<template>
    <v-app>
      <v-container>
        <!-- Loop through each company -->
        <div v-for="(company, companyIndex) in companies" :key="`company-${companyIndex}`">
          <h2>{{ company.name }}</h2>
  
          <!-- Timeline with consistent alignment -->
          <v-timeline dense>
            <!-- Loop through each position -->
            <v-timeline-item fill-dot dot-color="#ffff33" size="x-small" v-for="(position, positionIndex) in company.positions" :key="`position-${positionIndex}`">
              
              <!-- Year as main content on the left side -->
              <div class="pt-1 headline font-weight-bold">{{ position.year }}</div>
  
              <!-- Position title and details on the right side -->
              <v-card @click="toggleDetails(companyIndex, positionIndex)" class="mb-2">
                <v-card-title class="headline font-weight-light">{{ position.title }}</v-card-title>
                <v-expand-transition>
                  <v-card-text v-if="position.showDetails">
                    <div>Job Description</div>
                    <ul>
                      <li v-for="(item, itemIndex) in position.description" :key="`desc-item-${itemIndex}`">
                        {{ item }}
                      </li>
                    </ul>
                    <div>Tools Used</div>
                    <ul>
                      <li v-for="(tool, toolIndex) in position.tools" :key="`tool-item-${toolIndex}`">
                        {{ tool }}
                      </li>
                    </ul>
                  </v-card-text>
                </v-expand-transition>
              </v-card>
            </v-timeline-item>
          </v-timeline>
        </div>
      </v-container>
    </v-app>
  </template>
  
  <script>
  export default {
    data() {
      return {
        defaultColor: '#ffff33',
        activeColor: '#33ff33',
        companies: [
      {
        name: "Swan Foresight Pty. Ltd.",
        activeStep: 2,
        positions: [
          {
            showDetails: false,
            year: "Dec'22 - Feb'23",
            title: 'Intern',
            description: 
            [
                "Understand the business / functional user stories and suggest changes to automate the vulnerability and security testing",
                "Agree on the automation scripts work required and draft the technical user stories",
                "Record the automated scanning and testing reports and present them.",
                "Support in designing and building the operations and security dashboard",
            ],
            tools :
            [
                "Python",
                "MS Teams",
                "Azure DevOps",
                "Jira",
            ]
          },
          {
            showDetails: false,
            year: "Feb'23 - May'23",
            title: 'Security Automation Programmer',
            description: 
            [
                "Agree on the automation scripts work required and draft the technical user stories",
                "Record the automated scanning and testing reports and present them.",
                "Support in developing the web application security dashboard."
            ],
            tools :
            [
                "Python",
                "PostgreSQL",
                "Docker",
                "Wireshark",
                "Nmap",
                "Git",
                "Agile"
            ]
          },
          {
            showDetails: false,
            year: "May'23 - Now",
            title: 'Junior Software Developer',
            description: 
            [
                'Spearheaded frontend development of an energy sector security dashboard using Next.js.',
                'Expertly interfaced with APIs on AWS, employing Postman for validation and seamless integration.',
                'Administered application database using Prisma ORM in conjunction with AWS RDS, ensuring data integrity.',
                'Integrated robust user authentication with NextAuth & Keycloak enhancing security and user experience.',
                'Provided AWS services cost planning and infrastructure architecture insights for optimized system operations.',
                'Responsible for Docker containerization, ensuring efficient and consistent deployment environments.',
                'Automated server provisioning, streamlining the deployment process for enhanced system reliability.'
            ],
            tools: 
            [
                'Next.js',
                'React',
                'Postman',
                'AWS',
                'Docker',
                'Keycloak',
                'Git',
                'Ansible',
                'Agile'
            ]         
        },
        ]
      },
      {
        name: "Swinburne Capstone Project",
        activeStep: 0,
        positions: 
        [
            {
            showDetails: false,
            year: "Jan'23 - Dec'23",
            title: 'Developer',
            description: 
            [
                "Studied different security frameworks and standards to understand the security requirements of the project.",
                "Conducted research on Incident Response best practices to understand the requirements of the project.",
                "Designed a proprietary algorithm to evaluate incident response exercises leveraging client-specific datasets.",
                "Engineered the scoring system using R and ensured its robustness through tesFhat evaluations.",
                "Pioneered a web-based dashboard interface to provide a visual representation of outcomes, optimizing user accessibility to critical security metrics.",
            ],
            tools :
            [
                "R",
                "Mitre Attack Framework",
                "Bash",
                "Trello",
                "Agile",
            ]
          },
        ]
      },
      {
        name: "The Perfect Landlord",
        activeStep: 0,
        positions: 
        [
            {
            showDetails: false,
            year: "Jan'23 - Mar'23",
            title: 'Intern',
            description: 
            [
                "Develop new user-facing features using Vue.js",
                "Build reusable components and libraries for future use",
                "Collaborate with designers to ensure the technical feasibility of UI/UX designs",
                "Maintain healthy repository of Version Control System",
                "Understand the business needs and maintain communcation with the client",
            ],
            tools :
            [
                "VueJS",
                "Django Rest Framework",
                "Git",
                "Figma",
            ]
          },
        ]
      }
      // ... additional companies as needed
    ],
      };
    },
    methods: {
      toggleDetails(companyIndex, positionIndex) {
      const position = this.companies[companyIndex].positions[positionIndex];
      position.showDetails = !position.showDetails;
    },
      setActiveStep(company, step) {
        company.activeStep = step;
      },
      changeStep(company, direction) {
        const newStep = company.activeStep + direction;
        if (newStep >= 0 && newStep < company.positions.length) {
          company.activeStep = newStep;
        }
      },
      getStepStyle(company, positionIndex) {
        if (company.activeStep === positionIndex) {
      return {
        color: '#33ff33', // Active step text color
        // You can add more style properties here
      };
      } 
     else {
      return {
        color: '#ffff33', // Default step text color
        // Other default styles
      };
    }
    },
    },
  };
  </script>
  
  <style scoped>
  * {
    background-color: #212121;
    color: #ffff33;
    width: 100%;
  }
  
  h2{
    color: #33ff33;
  }
  .v-stepper-vertical{
    background-color: transparent;
    width: 100vw;
  }
  
  .v-stepper-header {
    display: flex;
    padding: 2rem;
  }
  
  .v-stepper-content {
    display: flex;
    justify-content: space-around;
    align-items: center;
    font-size: 20rem;

  }

  .v-stepper-item{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    
  }
  
  /* Smaller text for timeline content */
  .v-timeline-item p,
  .v-timeline-item ul,
  .v-timeline-item .text-h6 {
    font-size: 18px; /* Adjust this value as needed */
  }


  /* Style for the timeline icons */
  .v-timeline-item .v-icon {
    font-size: 24px; /* Adjust the font size of the icon */
    color: #4caf50; /* Color of the icon */
  }

  /* Style for the timeline icon background and border */
  .v-timeline-item .v-timeline-item__icon {
    background-color: #ffff33; /* Background color of the icon */
    border: 2px solid #4caf50; /* Border color and size */
  }

  /* Media query for small screens (e.g., phones) */
  @media (max-width: 600px) {
    /* Adjust font sizes for smaller screens */
    .v-timeline-item p,
    .v-timeline-item ul,
    .v-timeline-item .text-h6,
    .v-timeline-item .v-card-title {
      font-size: 12px;
    }

    /* Adjust icon sizes for smaller screens */
    .v-timeline-item .v-icon {
      font-size: 18px;
    }

    /* Adjust icon container for smaller screens */
    .v-timeline-item .v-timeline-item__icon {
      width: 24px;
      height: 24px;
      line-height: 24px;
    }
}

  </style>
  