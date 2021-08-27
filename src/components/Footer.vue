<template>
    <footer>
        <p>codes @ <a href="https://github.com/Cyebukayire/Task-Tracker">Task Tracker</a></p>
        <router-link to="/about">About</router-link>
    </footer>
</template>

<style>
    a {
        text-decoration: none;
    }
    a:link {
        color: rgb(97, 165, 211);
    }

    a:visited {
    color: rgb(121, 206, 121);
    }

    a:hover {
    color: rgb(241, 163, 202);
    }

    a:active {
    color: rgb(136, 197, 238);
    }

    footer {
        margin-top: 30px;
        text-align: center;
    }
</style>