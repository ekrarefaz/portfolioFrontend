<template>
    <v-app>
      <v-container>
        <!-- Loop through each company -->
        <div v-for="(company, companyIndex) in companies" :key="`company-${companyIndex}`">
          <h2>{{ company.name }}</h2>
          <v-stepper v-model="company.activeStep" vertical>
            <!-- Stepper header for selecting positions -->
            <v-stepper-header>
                <template v-for="(position, positionIndex) in company.positions" :key="`step-title-${positionIndex}`">
                  <v-stepper-step
                    :complete="company.activeStep > positionIndex"
                    :step="positionIndex"
                    @click="setActiveStep(company, positionIndex)"
                    :style="getStepStyle(company, positionIndex)"
                  >
                    {{ position.title }}
                  </v-stepper-step>
                  <v-divider v-if="positionIndex < company.positions.length - 1"></v-divider>
                </template>
            </v-stepper-header>
            
            <!-- Stepper content for showing descriptions -->
            <v-stepper-items>
                <v-stepper-content
                v-for="(position, positionIndex) in company.positions"
                :key="`step-content-${positionIndex}`"
                :step="positionIndex"
              >
                <div v-if="company.activeStep === positionIndex">
                  <v-card flat class="mb-4">
                    <!-- Job Description -->
                    <v-card-title>Job Description</v-card-title>
                    <v-card-text>
                      <ul>
                        <li v-for="(item, itemIndex) in position.description" :key="`desc-item-${itemIndex}`">
                          {{ item }}
                        </li>
                      </ul>
                    </v-card-text>
            
                    <!-- Tools Used -->
                    <v-card-title>Tools Used</v-card-title>
                    <v-card-text>
                      <ul>
                        <li v-for="(tool, toolIndex) in position.tools" :key="`tool-item-${toolIndex}`">
                          {{ tool }}
                        </li>
                      </ul>
                    </v-card-text>
                  </v-card>
                </div>
              </v-stepper-content>
            </v-stepper-items>
          </v-stepper>
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
        name: "Swan Foresight Pty. Ltd. (2023 - Current)",
        activeStep: 2,
        positions: [
          {
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
        name: "Swinburne Capstone Project (2023)",
        activeStep: 0,
        positions: 
        [
            {
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
        name: "The Perfect Landlord Dec'22 - Mar'23",
        activeStep: 0,
        positions: 
        [
            {
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
  
  .v-card-title {
    font-weight: bold;
  }

  .active-step {
    color: #33ff33 
  }
  
  .active-step .v-stepper__step {
    /* Adjust these styles according to your needs */
    background-color: #33ff33 !important; /* Force override */
    color: #212121 !important;
  }

  .active-step .v-stepper__step--active {
    color: #33ff33 !important;
  }

  .v-card-text {
    font-size: 20px; /* Set the desired font size */
  }

  /* If you want to specifically target list items */
  .job-description li, .tools-list li {
    font-size: 16px; /* Set the desired font size */
  }

  /* Additional styles to match your theme */
  </style>
  