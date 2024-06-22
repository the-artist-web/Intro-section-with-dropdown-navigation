<template>
    <nav class="navbar" data-navbar>
        <button @click="noneMenu()" class="close-menu">
            <img src="../assets/images/icon-close-menu.svg" alt="icon-close-menu">
        </button>

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
</template>

<script>
export default {
    name: "Aside",
    data() {},
    methods: {
        noneMenu: function() {
            document.querySelector("[data-navbar]").classList.remove("active");
            document.querySelector("[data-overflow]").classList.remove("active");
        }
    }
}
</script>

<style scoped>
    .navbar {
        position: fixed;
        background-color: var(--Almost-White);
        padding: 20px;
        top: 0;
        right: -1000px;
        bottom: 0;
        height: 100vh;
        width: 250px;
        display: flex;
        flex-direction: column;
        gap: 30px;
        z-index: 12;
        transition: .6s;
    }
    .navbar.active {
        right: 0;
        transition: .6s;
    }
    .navbar .close-menu { 
        background-color: var(--Almost-White);
        position: absolute;
        padding: 20px;
        height: 70px;
        width: 100%;
        top: 0;
        right: 0;
        left: 0;
        display: flex;
        align-items: center;
        justify-content: end;
    }
    .navbar .navbar-list {
        margin-top: 70px;
        display: flex;
        flex-direction: column;
        gap: 20px;
    }
    .navbar .navbar-list .navbar-item .navbar-link {
        display: flex;
        align-items: center;
        font-size: 16px;
        font-weight: 600;
        gap: 10px;
        transition: .4s;
    }
    .navbar .navbar-list .navbar-item .navbar-link:hover {
        opacity: 0.7;
        transition: .4s;
    }
    .navbar .navbar-list .navbar-item .navbar-link .icon-arrow-up { display: none; }

    .navbar .navbar-list .navbar-item .navbar-link:where(:hover, :focus-visible) .icon-arrow-up { display: block; }

    .navbar .navbar-list .navbar-item .navbar-link:where(:hover, :focus-visible) .icon-arrow-down { display: none; }

    .navbar .navbar-list .navbar-item .back-drop-down {
        padding-left: 30px;
        display: flex;
        flex-direction: column;
        margin-top: 20px;
        overflow: hidden;
        height: 0;
        gap: 15px;
        transition: .4s;
    }
    .navbar .navbar-list .navbar-item .back-drop-down::-webkit-scrollbar { display: none; }

    .navbar .navbar-list .navbar-item:hover .back-drop-down {
        height: auto;
        transition: .4s;
    }
    .navbar .navbar-list .navbar-item .back-drop-down .back-drop-link {
        display: flex;
        align-items: center;
        color: var(--Medium-Gray);
        font-size: 16px;
        font-weight: 600;
        gap: 15px;
        transition: .4s;
    }
    .navbar .navbar-list .navbar-item .back-drop-down .back-drop-link:hover {
        color: var(--Almost-Black);
        transition: .4s;
    }
    .navbar .navbar-btn{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 10px;
    }
    .navbar .navbar-btn .btn {
        width: 100%;
        font-size: 16px;
        font-weight: 600;
        padding: 10px 20px;
        border-radius: 14px;
        color: var(--Medium-Gray);
        transition: .4s;
    }
    .navbar .navbar-btn .btn:hover {
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
</style>