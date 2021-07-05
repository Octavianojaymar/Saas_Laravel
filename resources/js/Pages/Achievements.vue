<template>
    <nav class="">
        <div class="max-w-7xl mx-auto">
            <div class="flex justify-between">
                <div class="flex">  
                    <div>
                        <a href="/" class="flex items-center text-olive-500 hover:text-olive-600 py-4 px-3 transition duration-300">
                            <path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z" />
                             <img src="/images/Saas logo.png" alt="" class="h-5 w-5" style= "width: 100px; height: 100px">
                            <span class="text-xl font-bold " style="color: black">
                                Guidance Counseling
                            </span>
                        </a>
                    </div>  
                </div>
                <div class="hidden lg:flex items-center uppercase space-x-20 text-olive-500 font-semibold">
                    <div>
                        <a href="/services" class="hover:text-gray-900 transition duration-300" style="color: black">services</a>    
                    </div>
                    <div>
                        <a href="/achievements" class="hover:text-gray-900 transition duration-300" style="color: black">achievements</a>  
                    </div>
                    <div>
                        <a href="/careers" class="hover:text-gray-900 transition duration-300" style="color: black">careers</a>
                    </div>
                    <div v-if="!$page.props.user">
                        <a :href="route('login')" class="rounded-full bg-olive-400 hover:bg-olive-600 text-white px-6 p-2 shadow-lg shadow-sm transition duration-300" style="color: black; background-color: #9FEDD7">login</a>  
                    </div>
                    <div v-if="!$page.props.user">
                        <a :href="route('register')" class="rounded-full bg-olive-400 hover:bg-olive-600 text-white px-6 p-2 shadow-lg shadow-sm transition duration-300" style="color: black; background-color: #9FEDD7">register</a>  
                    </div>
                </div>
                <div class="lg:hidden flex items-center">
                    <button class="mobile-menu-button">
                       <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-black bg-gray-100" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                        </svg>
                    </button>
                </div>
            </div>       
            
        </div>
        <div class="mobile-menu lg:hidden hidden ml-2 uppercase">
            <a href="/services" class="block py-1 text-md hover:text-gray-900 text-olive-500 transition duration-300">services</a> 
            <a href="/achievements" class="block py-1 text-md hover:text-gray-900 text-olive-500 transition duration-300">achievements</a> 
            <a href="/careers" class="block py-1 text-md hover:text-gray-900 text-olive-500 transition duration-300">careers</a>
            <a :href="route('login')" class="py-2 px-2 block rounded-full bg-olive-400 hover:bg-olive-600 text-white  shadow-lg shadow-sm transition duration-300">login</a>  
            <a :href="route('register')" class="py-2 px-2 block mt-1 rounded-full bg-olive-400 hover:bg-olive-600 text-white shadow-lg shadow-sm transition duration-300 mb-2">register</a>  
        </div>
    </nav>
    <div class="text-lg font-semibold bg-sepia-300 py-5 px-5 lg:ml-10 lg:mr-10 rounded mt-20" style="background-color: #EDC7B7">
        <p class="">The Online Guidance Counseling Application was developing to enable students enhance the skills necessary to cope with changing situations, diverse members of school communities and make right choices. It was also aimed to help the management of institutions satisfy the identified needs and to better equipped for proper administration and development of students with great academic achievements. This will easily integrate into mainstream activities of society after graduation. It is a very helpful tool for the current situation which is the global pandemic caused by COVID-19, with the help of Online Guidance Counseling Application the students can communicate with the counselor through online base platform.</p>
    </div>
</template>
<script>
    export default {
 
    mounted(){
            const btn = document.querySelector('button.mobile-menu-button')
            const menu = document.querySelector('.mobile-menu')
            btn.addEventListener("click",()=>{
            menu.classList.toggle("hidden");
            });
            new Splide( '#card-slider',{
                type:'loop',
                speed: 600,
                perPage:1
    
                
            } ).mount();
        }
}
</script>