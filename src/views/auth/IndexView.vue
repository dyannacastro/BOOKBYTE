<script setup>
import { useDisplay } from 'vuetify'

const { mobile } = useDisplay()
</script>

<template>
    <v-app>
      <!-- Navbar Section -->
      <v-app-bar app color="black" flat>
        <v-container>
          <v-row>
            <v-spacer></v-spacer>
            <v-btn color="purple mt-10" RouterLink to="/register" class="btn-link">
                Get Started
              </v-btn>           
            <v-btn color="purple mt-10" dark RouterLink to="/login">
                login
            </v-btn>
          </v-row>
        </v-container>
      </v-app-bar>
  
      <!-- Hero Section -->
      <v-container class="mt-16 text-center">
        <v-row align="center" justify="center">
          <v-col cols="12" md="12">
            <v-img
              src="/images/book-logo.png"
              class="circle-logo mb-4"
              max-width="300"
            ></v-img>
          </v-col>
        </v-row>
      </v-container>
  
      <!-- Features Section -->
      <v-container>
        <v-row>
          <v-col cols="12" md="6">
            <v-card>
              <v-card-title class="custom-title">Comprehensive Technology Book Library</v-card-title>
              <v-card-text>
                BOOKBYTE offers a wide selection of books focused on technology topics like programming languages (Python, JavaScript, etc.), web development, software engineering, data science, and more. Users can search for books based on categories, titles, authors, or specific tech topics, ensuring they can easily find the resources they need.
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12" md="6">
            <v-card>
              <v-card-title class="custom-title"> "Add to Favorites" Feature</v-card-title>
              <v-card-text>
                Users can mark books as Favorites to create a personalized collection of their most preferred or frequently used books. This feature allows easy access to their favorite programming guides, tech tutorials, or reference materials without needing to search for them again. The Favorites list is saved in the user's favorite page, giving them quick access to the books they are currently reading or want to revisit in the future.
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12" md="6">
            <v-card>
              <v-card-title class="custom-title">Ideal Resource for Students</v-card-title>
              <v-card-text>
                BOOKBYTE is particularly beneficial for students studying technology-related fields. With its wide range of up-to-date books and learning materials, students can easily find textbooks, tutorials, and reference guides on programming, software development, data science, and more. The platform's "Favorites" feature also allows students to save essential resources for quick access, making it easier for them to organize their study materials and revisit important content during exams or project work.
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12" md="6">
            <v-card>
              <v-card-title class="custom-title">Search and Filter by Technology Topics</v-card-title>
              <v-card-text>
                BOOKBYTE offers a user-friendly search and filter feature that allows users to search for books by specific programming languages, tech frameworks, or topics like cloud computing, cybersecurity, or AI. This helps users find the most relevant books based on their area of interest or learning goals.
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>

        <!-- Book Gallery Section -->
    <v-container class="mt-16">
      <v-row>
        <v-col v-for="book in books" :key="book.id" cols="12" sm="4" md="4">
          <v-card class="book-card">
            <v-img :src="book.image" class="book-image" contain></v-img>
            <v-card-title class="book-title">{{ book.title }}</v-card-title>
            <v-card-subtitle>{{ book.author }}</v-card-subtitle>
            <v-card-text>{{ book.description }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Terms of Use Section -->
    <v-container class="mt-16">
      <v-row>
        <v-col cols="12">
          <v-card flat class="terms-card">
            <v-card-title class="term-n-use">Terms of Use</v-card-title>
            <v-card-text>
                By accessing and using this website, you agree to the following terms and conditions. The platform allows users to search for and read books online. All content available through the website may be protected by copyright laws, and users should be aware that the availability of books for reading may vary by region.
              <br/><br/>
                The website is designed for use by human users only. Automated tools or bots that scrape or misuse the platform may be blocked from accessing the site. To ensure a smooth experience and maintain platform integrity, cookies and related technologies may be used.
              <br/><br/>
                Users are permitted to search for and read books on the platform for personal, non-commercial use. Any redistribution of content or use beyond personal reading is prohibited without proper authorization from the copyright holder.
              <br/><br/>
                By using this platform, you consent to the collection of data as outlined in our Privacy Policy, and you agree to comply with these Terms of Use. Violation of these terms may result in the suspension of access to the site.
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>

     <!-- Social Media Section -->
<v-row justify="center" class="mt-4">
  <v-btn icon class="mx-4 social-btn">
    <v-icon>mdi-facebook</v-icon>
  </v-btn>
  <v-btn icon class="mx-4 social-btn">
    <v-icon>mdi-twitter</v-icon>
  </v-btn>
  <v-btn icon class="mx-4 social-btn">
    <v-icon>mdi-email</v-icon>
  </v-btn>
  <v-btn icon class="mx-4 social-btn">
    <v-icon>mdi-whatsapp</v-icon>
  </v-btn>
</v-row>
    </v-container>
    </v-app>
  </template>

  
  
<script>
export default {
  name: "index",
  data() {
    return {
      books: [
        {
          id: 1,
          title: "Introduction to Python",
          author: "Ethem Mining",
          image: "/images/python.webp",
          description: "Learn the basics of Python programming with this comprehensive guide.",
        },
        {
          id: 2,
          title: "Programming",
          author: "Alexander Bell",
          image: "/images/programming.jpg",
          description: "Deep dive into Programming language features and techniques.",
        },
        {
          id: 3,
          title: "Data Analysis",
          author: "Ali Abdulhussein",
          image: "/images/dataanalytic.png",
          description: "Explore the world of data analysis, machine learning, and statistics.",
        },
        {
          id: 4,
          title: "Cyber Security",
          author: "Mary Manjikian",
          image: "/images/cybersec.webp",
          description: "A comprehensive guide to protecting digital information and defending against cyber threats in today’s interconnected world.",
        },
        {
          id: 5,
          title: "Development",
          author: "Radu Nicoara",
          image: "/images/webdev.jpg",
          description: "Learn the essentials of web development, from foundational coding to advanced frameworks, to create dynamic and modern web applications",
        },
        {
          id: 6,
          title: "Business",
          author: "S. Christian Albright / Wayne L. Winston",
          image: "/images/business.jpg",
          description: "An insightful guide to data-driven decision-making, helping you navigate the complexities of modern business strategies and analytics.",
        },
      ],
    };
  },
};
</script>
  
  <style>
  body {
    background-color: black; /* Sets the entire background to black */
    color: white; /* Ensures all text is visible on the black background */
  }
  
  h1, p {
    color: white;
    padding-bottom: 10px;
  }
  .circle-logo {
    border-radius: 50%;
    border: 2px solid white;
    padding: 20px;
  }
  
  .v-application {
    background-color: black !important; /* This ensures that Vuetify components follow the black background */
  }

  .v-card {
    background-color: black;
    color: white;
  }

  .custom-title {
  font-size: 25px; 
  color: plum; 
  font-weight: bold;
}

.book-title {
  color: plum;
}

.book-image {
  width: 50%;  
  height: 50%; 
  object-fit: cover; 
}
.term-n-use {
    font-size: 1.5rem;
}

.terms-card {
  color: white;
  font-weight: 200;
}

.v-card-text a {
  color: #90caf9; /* Light blue for links */
  text-decoration: underline;
}

.social-btn .v-icon {
  transition: color 0.3s ease;
}

.social-btn:hover .v-icon {
  color: plum; /* Change color on hover */
}

.social-btn:active .v-icon {
  color: purple; /* Change color when clicked */
}

</style> "