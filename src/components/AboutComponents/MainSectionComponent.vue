<template>
    <v-container>
      <v-row justify="center">
        <v-col cols="12" md="10">
          <v-card class="about-card" outlined>
            <v-card-title class="headline mb-3">
              About Ekrar Efaz
            </v-card-title>
            <v-card-text class="about-text">
              <p>Welcome to my digital domain, where passion for Cyber-Security and mastery in Computer Science converge. As a final-year student, I'm on a spirited journey through the realms of Secure Software Development, Scalable Software Architectures, and the transformative world of DevOps.</p>
              <p>My current focus is a pioneering project: developing a Distributed Energy Resource Security Dashboard, blending professional acumen with academic rigor. Concurrently, I'm delving into the intricacies of GoLang and concurrent programming.</p>
              <p>My skill set spans from Object-Oriented Programming principles to diverse software architecture patterns like MVC and Microservices. I thrive in automation, utilizing Python, Bash, and Ansible, and excel in backend web development with Django and t3Stack. In database design, I specialize in MySQL, ensuring data integrity and efficiency.</p>
              <p>In the cloud, I navigate AWS services with a focus on backend deployment and security. My programming expertise extends across C++, Typescript, Python, and Ruby. Quality is my mantra in software development, and I am adept in containerization using Docker.</p>
              <p>My dedication to Cyber-Security is deep-rooted, encompassing Linux System Hardening, network security, forensic investigation, and understanding malware and threat landscapes.</p>
              <p>As a Linux enthusiast, I am skilled in advanced terminal commands, Bash scripting, and configuring servers and security protocols.</p>
              <p>Join me in exploring the intersection of technology and innovation, where every challenge is an opportunity to learn, grow, and create. Welcome to my world, where coding meets creativity and the future of tech takes shape.</p>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <style scoped>
  .about-card {
    background-color: #212121;
    color: #ffff33;
    border-radius: 10px;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  }
  
  .about-text p {
    font-size: 1.7em;
    line-height: 1.6;
    margin-bottom: 1em;
  }
  
  .headline {
    color: #33ff33;
    font-size: 2em;
    text-align: center;
  }
  
  @media (max-width: 600px) {
    .headline {
      font-size: 1.5em;
    }
    .about-text p {
      font-size: 1em;
    }
  }
  </style>
  