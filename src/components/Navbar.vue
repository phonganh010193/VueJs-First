<template>
    <nav 
        :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg', 'd-flex', 'justify-content-between']"
    >
        <div class="d-flex">
            <div class="navbar-header">
                <a class="navbar-brand" href="#">My Vue</a>
            </div>
            <ul class="navbar-nav">
                <li class="nav-item" v-for="(page, index) in pages" :key="index">
                    <a 
                        class="nav-link" 
                        :class="{active: activePage == index}"
                        :href="page.link.url"
                        :title="`This link goes to ${page.link.title}`"
                        @click.prevent="navLinkClick(index)"
                    >{{page.link.title}}</a>
                </li>
            </ul>
        </div>
        <div>
            <button 
                class="btn btn-primary"
                @click.prevent="changeTheme()"
            >Toggle NavBar</button>
        </div>
    </nav>
</template>
<script>
    export default {
        props: ['pages', 'activePage', 'navLinkClick'],
        data() {
            return {
                theme: 'light',
            }
        },
        methods: {
            changeTheme() {
                let theme = 'light'
                if(this.theme == 'light') {
                    theme = 'dark'
                }
                this.theme = theme;
            }
        },
    }
</script>