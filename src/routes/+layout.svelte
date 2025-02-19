<script>
    // import { onNavigate } from '$app/navigation';
    import { page } from '$app/stores';
    import "/src/app.css";
    import { fade } from 'svelte/transition';
    import Device from 'svelte-device-info'; 


//     onNavigate((navigation) => {
// 	if (!document.startViewTransition) return;

// 	return new Promise((resolve) => {
// 		document.startViewTransition(async () => {
// 			resolve();
// 			await navigation.complete;
// 		});
// 	});
// });




</script>

<meta name="viewport" content="width=device-width, initial-scale=0.7">


<div class="bg-cover bg-center h-dvh bg-[url('/images/bkuc.webp')]">
    <nav class="absolute top-10 left-1/2 transform -translate-x-1/2 backdrop-blur-sm bg-white/30 text-2xl text-white font-bold flex rounded-2xl z-10 p-3 px-5">
        
        <ul class="flex space-x-10">
            <li>
                <a href="/" class="hover:text-blue-800" class:active={$page.url.pathname === '/'}>Acasa</a>
            </li>
            
            <!-- Lectii with a larger hitbox -->
            <li class="relative group">
                <!-- Invisible hitbox area -->
                <div class="absolute left-0 top-full w-full h-10 group-hover:block"></div>

                <!-- Lectii dropdown button -->
                <a class="hover:text-blue-800 flex items-center z-10 relative" class:active={$page.url.pathname.startsWith('/classes')}>
                    Lectii
                    <!-- Dropdown arrow icon -->
                    <svg class="ml-2 w-4 h-4" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                    </svg>
                </a>
                <ul class="absolute hidden group-hover:block bg-white/30 backdrop-blur-sm text-white rounded-2xl shadow-lg mt-4 -ml-2.5 space-y-2 p-4 min-w-max z-50">
                    <li><a href="/lesson1" class="hover:text-blue-800" class:active={$page.url.pathname === '/lesson1'}>Constituirea UE</a></li>
                    <li><a href="/lesson2" class="hover:text-blue-800" class:active={$page.url.pathname === '/lesson2'}>Institutiile UE</a></li>
                    <li><a href="/lesson3" class="hover:text-blue-800" class:active={$page.url.pathname === '/lesson3'}>Europa contemporană</a></li>
                </ul>
            </li>

            <li>
                <a href="/about" class="hover:text-blue-800" class:active={$page.url.pathname === '/about'}>Info</a>
            </li>
            <li>
                <a href="/contact" class="hover:text-blue-800" class:active={$page.url.pathname === '/contact'}>Contact</a>
            </li>
        </ul>
    </nav>

    <div class="opacity-0">.</div>
    <div class="opacity-0">.</div>
    <div class="opacity-0">.</div>
    <div class="opacity-0">.</div>
    <div class="opacity-0">.</div>




    <div class="pt-28 pb-20">
        <slot />
    </div>
</div>



<footer class="fixed bottom-4 left-1/2 -translate-x-1/2 backdrop-blur-md bg-white/20 text-white text-center py-2 px-5 z-50 rounded-2xl">
    <p class="text-l font-bold whitespace-nowrap">© istoria.top - Toate drepturile rezervate  Alpha V2.0</p>
</footer>


