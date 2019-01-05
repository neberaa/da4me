<template>
    <header class="header">
        <div class="container">
            <div class="left">
                <g-link :to="{ name: 'home' }" class="home-link">
                    <img 
                        :src="settings.logo"
                        :alt="settings.site_name" 
                        class="logo"
                        v-if="settings.logo"
                    />
                    <span class="site-name" v-else>
                        {{ settings.site_name }}
                    </span>
                </g-link>
            </div>
            <nav class="nav right">
                <g-link class="nav__link" :to="{ name: 'journal' }">Journal</g-link>
                <g-link class="nav__link" :to="{ name: 'about' }">Say Hi!</g-link>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
  data() {
    return {
      settings: require("../../data/theme.json")
    }
  }
}
</script>

<style scoped>
.header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 6rem;
}
.header > .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 100%;
}
.home-link {
    text-decoration: none;
}
.logo {
    height: 1.5rem;
}
.site-name {
    font-size: 0.9rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-decoration: none;
    text-transform: uppercase;   
}
.nav > * {
    font-size: 0.9rem;
    font-weight: 600;
    text-decoration: none;
    margin-top: 4px;
    margin-right: 3rem;
    padding-bottom: 4px;
    border-bottom: 1px solid;
    border-color: transparent;
    transition: border 0.15s;
}
.nav > *:last-of-type {
    margin: 0;
}
.nav > *:hover {
    border-color: black;
}
.nav > .active {
    border-color: black;
}
</style>