<template>
    <div :class="[isDarkMode ? 'dark' : '', 'min-h-screen font-sans']">
        <div class="bg-white dark:bg-gray-900 text-gray-900 dark:text-white transition-colors duration-300">
            <!-- Header -->
            <header
                class="fixed w-full bg-white/80 dark:bg-gray-900/80 backdrop-blur-sm z-50 transition-colors duration-300">
                <div class="container mx-auto px-4 py-4 flex justify-between items-center">
                    <div class="text-xl font-bold">
                        <span class="text-rose-600">Dev</span>Portfolio
                    </div>
                    <nav class="hidden md:flex space-x-8">
                        <a href="#accueil" class="hover:text-rose-600 transition-colors">Accueil</a>
                        <a href="#projets" class="hover:text-rose-600 transition-colors">Projets</a>
                        <a href="#ia-projets" class="hover:text-rose-600 transition-colors">Projets IA</a>
                        <a href="#contact" class="hover:text-rose-600 transition-colors">Contact</a>
                    </nav>
                    <div class="flex items-center space-x-4">
                        <button @click="toggleDarkMode"
                            class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-800 transition-colors">
                            <sun-icon v-if="isDarkMode" class="h-5 w-5" />
                            <moon-icon v-else class="h-5 w-5" />
                        </button>
                        <button @click="isMenuOpen = !isMenuOpen"
                            class="md:hidden p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-800 transition-colors">
                            <menu-icon class="h-5 w-5" />
                        </button>
                    </div>
                </div>
                <!-- Mobile menu -->
                <div v-if="isMenuOpen" class="md:hidden bg-white dark:bg-gray-900 transition-all duration-300">
                    <div class="container mx-auto px-4 py-4 flex flex-col space-y-4">
                        <a href="#accueil" @click="isMenuOpen = false"
                            class="hover:text-rose-600 transition-colors">Accueil</a>
                        <a href="#projets" @click="isMenuOpen = false"
                            class="hover:text-rose-600 transition-colors">Projets</a>
                        <a href="#ia-projets" @click="isMenuOpen = false"
                            class="hover:text-rose-600 transition-colors">Projets IA</a>
                        <a href="#contact" @click="isMenuOpen = false"
                            class="hover:text-rose-600 transition-colors">Contact</a>
                    </div>
                </div>
            </header>

            <!-- Hero Section -->
            <section id="accueil" class="relative min-h-screen flex items-center pt-16">
                <div class="absolute inset-0 overflow-hidden">
                    <div
                        class="absolute inset-0 bg-gradient-to-b from-rose-100/20 to-transparent dark:from-rose-900/10 dark:to-transparent">
                    </div>
                </div>
                <div class="container mx-auto px-4 py-16 relative z-10">
                    <div class="grid md:grid-cols-2 gap-8 items-center">
                        <div class="space-y-6"
                            :class="{ 'translate-y-0 opacity-100': isVisible, 'translate-y-10 opacity-0': !isVisible }"
                            style="transition: all 0.8s ease-out;">
                            <div
                                class="inline-block px-3 py-1 bg-rose-100 dark:bg-rose-900/30 text-rose-800 dark:text-rose-200 rounded-full text-sm font-medium">
                                Développeur Full-Stack & Passionné d'IA
                            </div>
                            <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight">
                                Bonjour, je suis <span class="text-rose-600">Votre Nom</span>
                            </h1>
                            <p class="text-lg md:text-xl text-gray-600 dark:text-gray-300">
                                Je crée des applications web innovantes et des solutions basées sur l'intelligence
                                artificielle.
                            </p>
                            <div class="flex space-x-4">
                                <a href="#contact"
                                    class="px-6 py-3 bg-rose-600 hover:bg-rose-700 text-white rounded-lg transition-colors shadow-lg hover:shadow-xl">
                                    Me Contacter
                                </a>
                                <a href="#projets"
                                    class="px-6 py-3 bg-white dark:bg-gray-800 hover:bg-gray-100 dark:hover:bg-gray-700 text-gray-900 dark:text-white rounded-lg border border-gray-200 dark:border-gray-700 transition-colors shadow-lg hover:shadow-xl">
                                    Voir Mes Projets
                                </a>
                            </div>
                            <div class="flex items-center space-x-4 pt-4">
                                <a href="#"
                                    class="text-gray-600 dark:text-gray-300 hover:text-rose-600 dark:hover:text-rose-400 transition-colors">
                                    <github-icon class="h-6 w-6" />
                                </a>
                                <a href="#"
                                    class="text-gray-600 dark:text-gray-300 hover:text-rose-600 dark:hover:text-rose-400 transition-colors">
                                    <linkedin-icon class="h-6 w-6" />
                                </a>
                                <a href="#"
                                    class="text-gray-600 dark:text-gray-300 hover:text-rose-600 dark:hover:text-rose-400 transition-colors">
                                    <twitter-icon class="h-6 w-6" />
                                </a>
                                <div class="text-gray-600 dark:text-gray-300 flex items-center">
                                    <phone-icon class="h-5 w-5 mr-2" />
                                    <span>+33 6 12 34 56 78</span>
                                </div>
                            </div>
                        </div>
                        <div class="relative"
                            :class="{ 'translate-y-0 opacity-100': isVisible, 'translate-y-10 opacity-0': !isVisible }"
                            style="transition: all 0.8s ease-out; transition-delay: 0.2s;">
                            <div
                                class="relative z-10 bg-white dark:bg-gray-800 p-2 rounded-2xl shadow-2xl transform rotate-3 hover:rotate-0 transition-transform duration-500">
                                <img src="https://via.placeholder.com/600x800" alt="Votre photo"
                                    class="rounded-xl w-full h-auto" />
                            </div>
                            <div
                                class="absolute -bottom-4 -right-4 bg-rose-100 dark:bg-rose-900/30 p-4 rounded-xl shadow-lg">
                                <code-icon class="h-8 w-8 text-rose-600" />
                            </div>
                            <div
                                class="absolute -top-4 -left-4 bg-blue-100 dark:bg-blue-900/30 p-4 rounded-xl shadow-lg">
                                <cpu-icon class="h-8 w-8 text-blue-600" />
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Projects Section -->
            <section id="projets" class="py-20 bg-gray-50 dark:bg-gray-800 transition-colors duration-300">
                <div class="container mx-auto px-4">
                    <div class="text-center mb-16">
                        <h2 class="text-3xl md:text-4xl font-bold mb-4">Mes Projets</h2>
                        <p class="text-lg text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
                            Découvrez une sélection de mes projets récents, mettant en valeur mes compétences en
                            développement web et mobile.
                        </p>
                    </div>

                    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <div v-for="(project, index) in projects" :key="index"
                            class="bg-white dark:bg-gray-900 rounded-xl shadow-lg overflow-hidden group hover:shadow-xl transition-all duration-300 transform hover:-translate-y-2"
                            :class="{ 'translate-y-0 opacity-100': isVisible, 'translate-y-10 opacity-0': !isVisible }"
                            :style="`transition: all 0.8s ease-out; transition-delay: ${0.1 * index}s;`">
                            <div class="relative overflow-hidden">
                                <img :src="project.image" :alt="project.title"
                                    class="w-full h-48 object-cover transition-transform duration-500 group-hover:scale-110" />
                                <div
                                    class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end">
                                    <div
                                        class="p-4 text-white transform translate-y-4 group-hover:translate-y-0 transition-transform duration-300">
                                        <div class="flex space-x-3">
                                            <a :href="project.demo"
                                                class="px-3 py-1 bg-rose-600 hover:bg-rose-700 rounded-full text-sm flex items-center">
                                                <external-link-icon class="h-3 w-3 mr-1" />
                                                Démo
                                            </a>
                                            <a :href="project.github"
                                                class="px-3 py-1 bg-gray-800 hover:bg-gray-700 rounded-full text-sm flex items-center">
                                                <github-icon class="h-3 w-3 mr-1" />
                                                GitHub
                                            </a>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="p-6">
                                <h3
                                    class="text-xl font-bold mb-2 group-hover:text-rose-600 transition-colors duration-300">
                                    {{ project.title }}</h3>
                                <p class="text-gray-600 dark:text-gray-300 mb-4">{{ project.description }}</p>
                                <div class="flex flex-wrap gap-2 mb-4">
                                    <span v-for="tech in project.technologies" :key="tech"
                                        class="px-3 py-1 bg-gray-100 dark:bg-gray-800 text-gray-800 dark:text-gray-200 rounded-full text-sm transform transition-transform duration-300 hover:scale-105 hover:bg-rose-100 dark:hover:bg-rose-900/30 hover:text-rose-800 dark:hover:text-rose-200">
                                        {{ tech }}
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- AI Projects Section -->
            <section id="ia-projets" class="py-20 bg-white dark:bg-gray-900 transition-colors duration-300">
                <div class="container mx-auto px-4">
                    <div class="text-center mb-16">
                        <h2 class="text-3xl md:text-4xl font-bold mb-4">Projets IA</h2>
                        <p class="text-lg text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
                            Explorez mes projets d'intelligence artificielle, où je combine ma passion pour le
                            développement et l'IA.
                        </p>
                    </div>

                    <div class="grid md:grid-cols-2 gap-8">
                        <div v-for="(project, index) in aiProjects" :key="index"
                            class="bg-gray-50 dark:bg-gray-800 rounded-xl shadow-lg overflow-hidden group hover:shadow-xl transition-all duration-300 transform hover:-translate-y-2 flex flex-col md:flex-row"
                            :class="{ 'translate-y-0 opacity-100': isVisible, 'translate-y-10 opacity-0': !isVisible }"
                            :style="`transition: all 0.8s ease-out; transition-delay: ${0.1 * index}s;`">
                            <div class="relative w-full md:w-2/5 overflow-hidden">
                                <img :src="project.image" :alt="project.title"
                                    class="w-full h-48 md:h-full object-cover transition-transform duration-700 group-hover:scale-110" />
                                <div
                                    class="absolute inset-0 bg-gradient-to-r from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                                    <div
                                        class="p-4 text-white transform -translate-x-4 group-hover:translate-x-0 transition-transform duration-300 opacity-0 group-hover:opacity-100">
                                        <div class="flex flex-col space-y-2">
                                            <a :href="project.demo"
                                                class="px-4 py-2 bg-rose-600 hover:bg-rose-700 rounded-lg text-sm flex items-center justify-center">
                                                <external-link-icon class="h-4 w-4 mr-2" />
                                                Voir la Démo
                                            </a>
                                            <a :href="project.github"
                                                class="px-4 py-2 bg-gray-800 hover:bg-gray-700 rounded-lg text-sm flex items-center justify-center">
                                                <github-icon class="h-4 w-4 mr-2" />
                                                Code Source
                                            </a>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="p-6 flex-1 relative overflow-hidden">
                                <div
                                    class="absolute top-0 right-0 w-24 h-24 bg-rose-600/10 rounded-full -mr-12 -mt-12 group-hover:scale-150 transition-transform duration-500">
                                </div>
                                <h3
                                    class="text-xl font-bold mb-2 group-hover:text-rose-600 transition-colors duration-300 relative">
                                    {{ project.title }}</h3>
                                <p class="text-gray-600 dark:text-gray-300 mb-4 relative">{{ project.description }}</p>
                                <div class="flex flex-wrap gap-2 mb-4 relative">
                                    <span v-for="tech in project.technologies" :key="tech"
                                        class="px-3 py-1 bg-rose-100 dark:bg-rose-900/30 text-rose-800 dark:text-rose-200 rounded-full text-sm transform transition-all duration-300 hover:scale-110 hover:shadow-md">
                                        {{ tech }}
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Contact Section -->
            <section id="contact" class="py-20 bg-gray-50 dark:bg-gray-800 transition-colors duration-300">
                <div class="container mx-auto px-4">
                    <div class="text-center mb-16">
                        <h2 class="text-3xl md:text-4xl font-bold mb-4">Me Contacter</h2>
                        <p class="text-lg text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
                            Vous avez un projet en tête ou souhaitez simplement discuter ? N'hésitez pas à me contacter
                            !
                        </p>
                    </div>

                    <div class="grid md:grid-cols-2 gap-8 max-w-4xl mx-auto">
                        <div class="bg-white dark:bg-gray-900 p-8 rounded-xl shadow-lg"
                            :class="{ 'translate-x-0 opacity-100': isVisible, 'translate-x-10 opacity-0': !isVisible }"
                            style="transition: all 0.8s ease-out;">
                            <form @submit.prevent="submitForm" class="space-y-4">
                                <div>
                                    <label for="name"
                                        class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Nom</label>
                                    <input type="text" id="name" v-model="form.name"
                                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-700 rounded-lg focus:ring-2 focus:ring-rose-500 focus:border-transparent bg-white dark:bg-gray-800 text-gray-900 dark:text-white"
                                        required />
                                </div>
                                <div>
                                    <label for="email"
                                        class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Email</label>
                                    <input type="email" id="email" v-model="form.email"
                                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-700 rounded-lg focus:ring-2 focus:ring-rose-500 focus:border-transparent bg-white dark:bg-gray-800 text-gray-900 dark:text-white"
                                        required />
                                </div>
                                <div>
                                    <label for="message"
                                        class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Message</label>
                                    <textarea id="message" v-model="form.message" rows="4"
                                        class="w-full px-4 py-2 border border-gray-300 dark:border-gray-700 rounded-lg focus:ring-2 focus:ring-rose-500 focus:border-transparent bg-white dark:bg-gray-800 text-gray-900 dark:text-white"
                                        required></textarea>
                                </div>
                                <button type="submit"
                                    class="w-full px-6 py-3 bg-rose-600 hover:bg-rose-700 text-white rounded-lg transition-colors shadow-lg hover:shadow-xl">
                                    Envoyer
                                </button>
                            </form>
                        </div>
                        <div class="bg-white dark:bg-gray-900 p-8 rounded-xl shadow-lg flex flex-col justify-center"
                            :class="{ 'translate-x-0 opacity-100': isVisible, '-translate-x-10 opacity-0': !isVisible }"
                            style="transition: all 0.8s ease-out;">
                            <div class="space-y-6">
                                <div class="flex items-start space-x-4">
                                    <mail-icon class="h-6 w-6 text-rose-600 mt-1" />
                                    <div>
                                        <h3 class="text-lg font-medium">Email</h3>
                                        <p class="text-gray-600 dark:text-gray-300">votre.email@exemple.com</p>
                                    </div>
                                </div>
                                <div class="flex items-start space-x-4">
                                    <phone-icon class="h-6 w-6 text-rose-600 mt-1" />
                                    <div>
                                        <h3 class="text-lg font-medium">Téléphone</h3>
                                        <p class="text-gray-600 dark:text-gray-300">+33 6 12 34 56 78</p>
                                    </div>
                                </div>
                                <div class="flex items-start space-x-4">
                                    <map-pin-icon class="h-6 w-6 text-rose-600 mt-1" />
                                    <div>
                                        <h3 class="text-lg font-medium">Localisation</h3>
                                        <p class="text-gray-600 dark:text-gray-300">Paris, France</p>
                                    </div>
                                </div>
                                <div class="pt-4">
                                    <h3 class="text-lg font-medium mb-3">Réseaux Sociaux</h3>
                                    <div class="flex space-x-4">
                                        <a href="#"
                                            class="text-gray-600 dark:text-gray-300 hover:text-rose-600 dark:hover:text-rose-400 transition-colors">
                                            <github-icon class="h-6 w-6" />
                                        </a>
                                        <a href="#"
                                            class="text-gray-600 dark:text-gray-300 hover:text-rose-600 dark:hover:text-rose-400 transition-colors">
                                            <linkedin-icon class="h-6 w-6" />
                                        </a>
                                        <a href="#"
                                            class="text-gray-600 dark:text-gray-300 hover:text-rose-600 dark:hover:text-rose-400 transition-colors">
                                            <twitter-icon class="h-6 w-6" />
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Footer -->
            <footer class="py-8 bg-gray-900 text-white">
                <div class="container mx-auto px-4">
                    <div class="flex flex-col md:flex-row justify-between items-center">
                        <div class="mb-4 md:mb-0">
                            <div class="text-xl font-bold">
                                <span class="text-rose-600">Dev</span>Portfolio
                            </div>
                            <p class="text-gray-400 mt-2">© {{ new Date().getFullYear() }} Tous droits réservés.</p>
                        </div>
                        <div class="flex space-x-6">
                            <a href="#accueil" class="hover:text-rose-600 transition-colors">Accueil</a>
                            <a href="#projets" class="hover:text-rose-600 transition-colors">Projets</a>
                            <a href="#ia-projets" class="hover:text-rose-600 transition-colors">Projets IA</a>
                            <a href="#contact" class="hover:text-rose-600 transition-colors">Contact</a>
                        </div>
                    </div>
                </div>
            </footer>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import {
    SunIcon, MoonIcon, MenuIcon, GithubIcon, LinkedinIcon, TwitterIcon,
    PhoneIcon, CodeIcon, CpuIcon, ExternalLinkIcon, MailIcon, MapPinIcon
} from 'lucide-vue-next';

// Dark mode toggle
const isDarkMode = ref(false);

const toggleDarkMode = () => {
    isDarkMode.value = !isDarkMode.value;
    localStorage.setItem('darkMode', isDarkMode.value);

    // Ajouter ou supprimer la classe 'dark' sur l'élément HTML
    if (isDarkMode.value) {
        console.log(isDarkMode);
        
        document.documentElement.classList.add('dark');
    } else {
        document.documentElement.classList.remove('dark');
    }
};

// Mobile menu
const isMenuOpen = ref(false);

// Visibility for animations
const isVisible = ref(false);

// Contact form
const form = ref({
    name: '',
    email: '',
    message: ''
});

const submitForm = () => {
    // Here you would typically send the form data to a server
    alert(`Merci ${form.value.name} ! Votre message a été envoyé.`);
    form.value = { name: '', email: '', message: '' };
};

// Projects data
const projects = ref([
    {
        title: "Application E-commerce",
        description: "Une plateforme e-commerce complète avec panier, paiement et gestion des commandes.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Vue.js", "Node.js", "MongoDB", "Stripe"],
        demo: "#",
        github: "#"
    },
    {
        title: "Dashboard Analytics",
        description: "Un tableau de bord interactif pour visualiser et analyser les données d'entreprise.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Vue.js", "D3.js", "Firebase", "Tailwind CSS"],
        demo: "#",
        github: "#"
    },
    {
        title: "Application Mobile",
        description: "Une application mobile cross-platform pour la gestion de tâches et la productivité.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Vue Native", "Expo", "Redux", "Firebase"],
        demo: "#",
        github: "#"
    },
    {
        title: "Site Web Responsive",
        description: "Un site web responsive pour une agence de design avec animations fluides.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Vue.js", "GSAP", "Tailwind CSS", "Netlify"],
        demo: "#",
        github: "#"
    },
    {
        title: "API RESTful",
        description: "Une API RESTful complète pour la gestion de contenu et l'authentification.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Node.js", "Express", "MongoDB", "JWT"],
        demo: "#",
        github: "#"
    },
    {
        title: "Progressive Web App",
        description: "Une PWA pour consulter les actualités avec fonctionnalités hors ligne.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Vue.js", "Workbox", "IndexedDB", "Netlify"],
        demo: "#",
        github: "#"
    }
]);

// AI Projects data
const aiProjects = ref([
    {
        title: "Système de Recommandation",
        description: "Un système de recommandation basé sur l'apprentissage automatique pour suggérer des produits personnalisés.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Python", "TensorFlow", "Flask", "Vue.js"],
        demo: "#",
        github: "#"
    },
    {
        title: "Chatbot IA",
        description: "Un chatbot intelligent utilisant le traitement du langage naturel pour répondre aux questions des utilisateurs.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Python", "NLTK", "Rasa", "Node.js"],
        demo: "#",
        github: "#"
    },
    {
        title: "Analyse de Sentiment",
        description: "Un outil d'analyse de sentiment pour évaluer les avis clients et les commentaires sur les réseaux sociaux.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Python", "Scikit-learn", "BERT", "Django"],
        demo: "#",
        github: "#"
    },
    {
        title: "Détection d'Objets",
        description: "Une application de détection d'objets en temps réel utilisant la vision par ordinateur.",
        image: "https://via.placeholder.com/600x400",
        technologies: ["Python", "OpenCV", "YOLO", "TensorFlow"],
        demo: "#",
        github: "#"
    }
]);

// Intersection Observer for animations
let observer;

onMounted(() => {
    // Check for saved dark mode preference
    const savedDarkMode = localStorage.getItem('darkMode');
    if (savedDarkMode === 'true') {
        isDarkMode.value = true;
        console.log(savedDarkMode);
        
        document.documentElement.classList.add('dark');
    }
    else {
        document.documentElement.classList.remove('dark');
    };

    // Set up intersection observer for animations
    observer = new IntersectionObserver(
        (entries) => {
            if (entries[0].isIntersecting) {
                isVisible.value = true;
            }
        },
        { threshold: 0.1 }
    );

    observer.observe(document.body);

    // Add smooth scrolling for anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
            e.preventDefault();
            const targetId = this.getAttribute('href');
            const targetElement = document.querySelector(targetId);
            if (targetElement) {
                window.scrollTo({
                    top: targetElement.offsetTop - 80,
                    behavior: 'smooth'
                });
            }
        });
    });

    // Parallax effect for hero section
    const handleScroll = () => {
        const scrollPosition = window.scrollY;
        const heroSection = document.querySelector('#accueil');
        if (heroSection) {
            const elements = heroSection.querySelectorAll('.relative');
            elements.forEach((el, index) => {
                const speed = 0.1 * (index + 1);
                el.style.transform = `translateY(${scrollPosition * speed}px)`;
            });
        }
    };

    window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
    if (observer) {
        observer.disconnect();
    }
    window.removeEventListener('scroll', handleScroll);
});
</script>

<style>
/* Base styles */
html {
    scroll-behavior: smooth;
}

/* Dark mode styles */
.dark {
    color-scheme: dark;
}

/* Animations */
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.animate-fadeIn {
    animation: fadeIn 0.8s ease-out forwards;
}

/* Custom scrollbar */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-track {
    background: #f1f1f1;
}

.dark ::-webkit-scrollbar-track {
    background: #2d3748;
}

::-webkit-scrollbar-thumb {
    background: #888;
    border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
    background: #555;
}

.dark ::-webkit-scrollbar-thumb {
    background: #4a5568;
}

.dark ::-webkit-scrollbar-thumb:hover {
    background: #718096;
}

/* Card animations */
@keyframes pulse {

    0%,
    100% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.05);
    }
}

.pulse-on-hover:hover {
    animation: pulse 2s infinite;
}

@keyframes float {
    0% {
        transform: translateY(0px);
    }

    50% {
        transform: translateY(-10px);
    }

    100% {
        transform: translateY(0px);
    }
}

.float-animation {
    animation: float 6s ease-in-out infinite;
}
</style>