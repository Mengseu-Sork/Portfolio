<template>
  <section
    id="contact"
    class="py-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-br from-sky-50 via-blue-50 to-indigo-100"
  >
    <div class="max-w-5xl mx-auto">
      <!-- Section Title -->
      <div class="text-center mb-12" ref="contactTitle">
        <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">Get In Touch</h2>
        <div class="w-20 h-1 bg-gradient-to-r from-sky-500 to-blue-600 mx-auto"></div>
      </div>

      <!-- Grid Layout -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
        <!-- Contact Info -->
        <div ref="contactInfoSection" class="animate-slideInLeft">
          <h3 class="text-2xl font-semibold text-center md:text-left text-gray-900 mb-6">
            Contact Information
          </h3>
          <div class="space-y-4">
            <div
              v-for="(contact, index) in contactInfo"
              :key="contact.type"
              class="flex items-center group animate-fadeInUp"
              :style="{ animationDelay: index * 0.1 + 's' }"
            >
              <!-- Icon Circle -->
              <div
                class="w-12 h-12 bg-gradient-to-br from-sky-500 to-blue-600 rounded-full flex-shrink-0 flex items-center justify-center mr-4 group-hover:scale-110 transition-transform duration-300"
              >
                <component :is="contact.icon" class="h-5 w-5 text-white" />
              </div>

              <!-- Text Wrapping -->
              <span
                class="text-gray-700 group-hover:text-sky-600 transition-colors duration-300 break-all w-full"
              >
                {{ contact.text }}
              </span>
            </div>
          </div>

          <div
            class="mt-8 animate-fadeInUp text-center md:text-left"
            style="animation-delay: 0.5s"
          >
            <h4 class="text-lg font-semibold text-gray-900 mb-4">Follow Me</h4>

            <div class="flex flex-wrap justify-center md:justify-start gap-4 sm:gap-6">
              <a
                v-for="(social, index) in socialLinks"
                :key="social.name"
                :href="social.link"
                target="_blank"
                rel="noopener noreferrer"
                class="w-12 h-12 bg-gradient-to-br from-sky-500 to-blue-600 rounded-full flex items-center justify-center text-white hover:shadow-2xl transition-transform duration-300 hover:scale-110 hover:rotate-12 animate-bounceIn"
                :style="{ animationDelay: `${index * 0.1 + 0.6}s` }"
              >
                <component :is="social.icon" class="h-5 w-5" />
              </a>
            </div>
          </div>
        </div>

        <!-- Contact Form -->
        <div ref="contactForm" class="animate-slideInRight">
          <Form @submit="submitForm" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Mail, Phone, MapPin, Github, Linkedin, Facebook } from "lucide-vue-next";
import Form from "@/components/Form.vue";

// Contact Info
const contactInfo = [
  {
    icon: Mail,
    type: "email",
    text: "mengseu.sork@student.passerellesnumeriques.org",
  },
  {
    icon: Phone,
    type: "phone",
    text: "+855 86 788 826",
  },
  {
    icon: MapPin,
    type: "address",
    text: "Street 371, phum Tropeang Chhuk, Sangkat Tek Thla, Khan Sen Sok, Phnom Penh",
  },
];

// Social Media Links
const socialLinks = [
  {
    name: "GitHub",
    icon: Github,
    link: "https://github.com/Mengseu-Sork",
  },
  {
    name: "LinkedIn",
    icon: Linkedin,
    link: "https://www.linkedin.com/in/mengseu-sork-5b4378345/",
  },
  {
    name: "Email",
    icon: Mail,
    link: "mailto:mengseu.sork@student.passerellesnumeriques.org",
  },
  {
    name: "Facebook",
    icon: Facebook,
    link: "https://www.facebook.com/sdack.drama",
  },
];

// Form Submission
const submitForm = (formData) => {
  alert("Thank you for your message! I will get back to you soon.");
  console.log("Form submitted:", formData);
};
</script>
