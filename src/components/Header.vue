<template>
    <!-- #OVERFLOW -->
    <div class="overflow" data-overflow></div>

    <!-- #HEADER -->
    <header class="header">
        <div class="container">
            <a href="#" class="logo">
                <img src="../assets/images/logo.svg" alt="logo" class="img-logo">
            </a>

            <nav class="navbar">
                <ul class="navbar-list">
                    <li class="navbar-item">
                        <a href="#" class="navbar-link">
                            <span class="span">Features</span>
                            <img src="../assets/images/icon-arrow-up.svg" alt="icon-arrow-up" class="icon-arrow-up">
                            <img src="../assets/images/icon-arrow-down.svg" alt="icon-arrow-down" class="icon-arrow-down">
                        </a>

                        <div class="back-drop-down">
                            <a href="#" class="back-drop-link">
                                <img src="../assets/images/icon-todo.svg" alt="icon-todo">
                                <span class="span">Todo List</span>
                            </a>

                            <a href="#" class="back-drop-link">
                                <img src="../assets/images/icon-calendar.svg" alt="icon-calendar">
                                <span class="span">Calendar</span>
                            </a>

                            <a href="#" class="back-drop-link">
                                <img src="../assets/images/icon-reminders.svg" alt="icon-reminders">
                                <span class="span">Reminders</span>
                            </a>

                            <a href="#" class="back-drop-link">
                                <img src="../assets/images/icon-planning.svg" alt="icon-planning">
                                <span class="span">Planning</span>
                            </a>
                        </div>
                    </li>

                    <li class="navbar-item">
                        <a href="#" class="navbar-link">
                            <span class="span">Company</span>
                            <img src="../assets/images/icon-arrow-up.svg" alt="icon-arrow-up" class="icon-arrow-up">
                            <img src="../assets/images/icon-arrow-down.svg" alt="icon-arrow-down" class="icon-arrow-down">
                        </a>

                        <div class="back-drop-down">
                            <a href="#" class="back-drop-link">History</a>

                            <a href="#" class="back-drop-link">Our Team</a>

                            <a href="#" class="back-drop-link">Blog</a>
                        </div>
                    </li>

                    <li class="navbar-item">
                        <a href="#" class="navbar-link">Careers</a>
                    </li>

                    <li class="navbar-item">
                        <a href="#" class="navbar-link">About</a>
                    </li>
                </ul>

                <div class="navbar-btn">
                    <button class="btn">Login</button>
                    <button class="btn btn-primary">Register</button>
                </div>
            </nav>

            <button @click="showMenu()">
                <img src="../assets/images/icon-menu.svg" alt="icon-menu" class="icon-menu">
            </button>
        </div>
    </header>

    <!-- #ASIDE -->
    <Aside />
</template>

<script>
import Aside from '@/components/Aside.vue'

export default {
    name: "Header",
    data() {},
    components: {
        Aside
    },
    methods: {
        showMenu: function() {
            document.querySelector("[data-overflow]").classList.add("active");
            document.querySelector("[data-navbar]").classList.add("active");
        }
    }
}
</script>

<style scoped>
    /* #OVERFLOW */
    .overflow {
        background-color: var(--Almost-Black);
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        width: 100%;
        height: 100vh;
        z-index: 11;
        opacity: 0;
        visibility: hidden;
        transition: .6s;
    }
    .overflow.active {
        opacity: 0.7;
        visibility: visible;
        transition: .6s;
    }

    /* #HEADER */
    .header .container {
        background-color: var(--Almost-White);
        display: flex;
        align-items: center;
        justify-content: space-between;
        height: 70px;
        width: 100%;
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        z-index: 10;
    }
    .header .container .navbar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-left: 80px;
        display: none;
        width: 100%;
        position: relative;
        z-index: 10;
    }
    .header .container .navbar .navbar-list {
        display: flex;
        align-items: center;
        gap: 50px;
    }
    .header .container .navbar .navbar-list .navbar-item { 
        position: relative; 
        z-index: 10;
        transition: .4s;
    }
    .header .container .navbar .navbar-list .navbar-item .navbar-link {
        display: flex;
        align-items: center;
        font-size: 16px;
        font-weight: 600;
        gap: 10px;
        transition: .4s;
    }
    .header .container .navbar .navbar-list .navbar-item .navbar-link:hover {
        opacity: 0.7;
        transition: .4s;
    }
    .header .container .navbar .navbar-list .navbar-item .navbar-link .icon-arrow-up { display: none; }

    .header .container .navbar .navbar-list .navbar-item .navbar-link:where(:hover, :focus-visible) .icon-arrow-up { display: block; }

    .header .container .navbar .navbar-list .navbar-item .navbar-link:where(:hover, :focus-visible) .icon-arrow-down { display: none; }

    .header .container .navbar .navbar-list .navbar-item .back-drop-down {
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 0 20px -5px var(--Medium-Gray);
        position: fixed;
        top: 60px;
        left: auto;
        display: flex;
        flex-direction: column;
        gap: 10px;
        z-index: 10;
        opacity: 0;
        visibility: hidden;
        transition: .4s;
    }
    .header .container .navbar .navbar-list .navbar-item:hover .back-drop-down {
        opacity: 1;
        visibility: visible;
        transition: .4s;
    }
    .header .container .navbar .navbar-list .navbar-item .back-drop-down .back-drop-link {
        display: flex;
        align-items: center;
        color: var(--Medium-Gray);
        font-size: 16px;
        font-weight: 600;
        z-index: 10;
        gap: 15px;
        transition: .4s;
    }
    .header .container .navbar .navbar-list .navbar-item .back-drop-down .back-drop-link:hover {
        color: var(--Almost-Black);
        transition: .4s;
    }
    .header .container .navbar .navbar-btn{
        display: flex;
        align-items: center;
        gap: 10px;
    }
    .header .container .navbar .navbar-btn .btn {
        font-size: 16px;
        font-weight: 600;
        padding: 10px 20px;
        border-radius: 14px;
        color: var(--Medium-Gray);
        transition: .4s;
    }
    .header .container .navbar .navbar-btn .btn:hover {
        color: var(--Almost-Black);
        transition: .4s;
    }
    .btn-primary {
        border: 2px solid var(--Medium-Gray);
        transition: .4s;
    }
    .btn-primary:hover {
        border: 2px solid var(--Almost-Black);
        transition: .4s;
    }

    /*---------------------------------------*\
      #MEDIA
    \*---------------------------------------*/

    /**
     * fit size 992px
     */
    @media screen and (min-width: 992px) { 
        .header .container .navbar { display: flex; }

        .icon-menu { display: none; }
    }
</style>