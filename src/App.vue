<template>
    <div class="container-fluid">
        <navbar
            :pages="pages"
            :active-page="activePage"
            :nav-link-click="(index) => activePage = index"
        ></navbar>
        <page-viewer
            :page="pages[activePage]"    
        ></page-viewer>
        </div>
</template>

<script>
    import PageViewer from './components/PageViewer.vue';
    import Navbar from './components/Navbar.vue';

    export default {
        components: {
            Navbar,
            PageViewer
        },
        data() {
            return {
                activePage: 0,
                pages: [
                    {
                        link:{title: "Home", url:"home.html"},
                        pageTitle: "HomePage",
                        content: "This is Home content",
                    },
                    {
                        link:{title: "About", url:"about.html"},
                        pageTitle: "AboutPage",
                        content: "This is About content",
                    },
                    {
                        link:{title: "Contact", url:"contact.html"},
                        pageTitle: "ContactPage",
                        content: "This is Contact content",
                    },
                ]
            }
        }
    }
    
</script>