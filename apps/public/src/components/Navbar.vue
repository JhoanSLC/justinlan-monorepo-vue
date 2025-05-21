<template>
    <section>
        <div class="drawer">
            <input id="my-drawer-3" type="checkbox" class="drawer-toggle" />
            <div class="drawer-content flex flex-col min-h-screen overflow-hidden">
                <!-- Navbar -->
                <div class="navbar mt-3 h-24 sticky lg:p-16 text-white text-2xl w-full">
                    <div class="mx-2 flex-1 px-2 text-5xl text-yellow-200" style="font-family: 'Ancizar serif'">J u s t i n L a n</div>
                    <div class="flex-none lg:hidden">
                        <label for="my-drawer-3" aria-label="open sidebar" class="btn btn-square btn-ghost">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                class="inline-block h-6 w-6 stroke-current">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M4 6h16M4 12h16M4 18h16"></path>
                            </svg>
                        </label>
                    </div>
                    <div class="hidden lg:flex flex-none">
                        <ul class="menu menu-horizontal text-4xl gap-6">
                            <li class="relative group">
                                <button @click="openDrawer" class="cursor-pointer hover:text-amber-200 transition">
                                    <p style="font-family: 'Ancizar serif'"> Menu </p>
                                    <span class="absolute left-0 -bottom-1 h-0.5 w-full bg-amber-200 scale-x-0 group-hover:scale-x-100 transition-transform origin-left"></span>
                                </button>
                            </li>
                            <li class="relative group">
                                <a href="#" class="hover:text-amber-200 transition inline-block relative">
                                    <p style="font-family: 'Ancizar serif'"> Perfil </p>
                                    <span
                                        class="absolute left-0 -bottom-1 h-0.5 w-full bg-amber-200 scale-x-0 group-hover:scale-x-100 transition-transform origin-left"></span>
                                </a>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
            <!-- Drawer Sidebar -->
            <div class="drawer-side h-full">
                <label for="my-drawer-3" aria-label="close sidebar" class="drawer-overlay"></label>
                <aside
                    class="bg-gradient-to-b from-amber-200 to-amber-100 shadow-lg min-h-full w-80 p-6 flex flex-col justify-between">
                    <ul class="space-y-4 text-lg font-medium">
                        <li>
                            <a class="flex items-center gap-3 hover:bg-amber-300 hover:text-black px-4 py-2 rounded transition-all duration-300"> Sidebar Item 1 </a>
                        </li>
                        <li>
                            <a class="flex items-center gap-3 hover:bg-amber-300 hover:text-black px-4 py-2 rounded transition-all duration-300"> Sidebar Item 2 </a>
                        </li>
                    </ul>
                    <!-- Bas du drawer -->
                    <div class="mt-auto pt-8 border-t text-center  border-amber-300 text-sm text-amber-800">
                        <p>&copy; 2025 Justin Lan.</p>
                    </div>
                </aside>
            </div>
        </div>
    </section>
</template>

<script setup>
function openDrawer() {
    const checkbox = document.getElementById('my-drawer-3');
    if (checkbox) checkbox.checked = true;
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Ancizar+Serif:ital,wght@0,300..900;1,300..900&family=Bebas+Neue&family=Syne+Mono&family=Underdog&display=swap');

/* Animation "jump" du texte au hover */
.menu-horizontal li.group>button,
.menu-horizontal li.group>a {
    display: inline-block;
    transition: transform 0.3s ease;
}

.menu-horizontal li.group:hover>button,
.menu-horizontal li.group:hover>a {
    animation: jump 0.3s ease forwards;
}

/* Animation keyframes pour le saut */
@keyframes jump {
    0% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-6px);
    }

    100% {
        transform: translateY(0);
    }
}
</style>
