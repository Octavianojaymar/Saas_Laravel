<template>
        <nav class="">
            <div class="max-w-7xl mx-auto" >
                <div class="flex justify-between">
                    <div class="flex">  
                        <div>
                            <a href="/" class="flex items-center text-olive-500 hover:text-olive-600 py-4 px-3 transition duration-300">
                                <path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z" />
                                <img src="/images/Saas logo.png" alt="" class="h-5 w-5" style= "width: 150px; height: 150px">
                                <span class="text-xl font-bold " style="font: book antiqua; color: black;">
                                   Guidance Counseling
                                </span>
                            </a>
                        </div>  
                    </div>
                    <div class="hidden lg:flex items-center uppercase space-x-10 text-olive-500 font-semibold">
                        <div>
                            <a href="/services" class="hover:text-gray-900 transition duration-300" style="color: black;">services</a>    
                        </div>
                        <div>
                            <a href="/achievements" class="hover:text-gray-900 transition duration-300" style="color: black;">achievements</a>  
                        </div>
                        <div>
                            <a href="/careers" class="hover:text-gray-900 transition duration-300" style="color: black;">careers</a>
                        </div>
                        <div>
                            <a href="/dashboard" class="hover:text-gray-900 transition duration-300" style="color: black;">dashboard</a>
                        </div>
                        <div v-if="!$page.props.user">
                            <a :href="route('login')" class="rounded-full bg-olive-400 hover:bg-olive-600 text-white px-6 p-2 shadow-lg shadow-sm transition duration-300" style="background-color: #9FEDD7; color: black;">login</a>  
                        </div>
                        <div v-if="!$page.props.user">
                            <a :href="route('register')" class="rounded-full bg-olive-400 hover:bg-olive-600 text-white px-6 p-2 shadow-lg shadow-sm transition duration-300" style="background-color: #9FEDD7; color: black;">register</a>  
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
                <a href="/services" class="block py-1 text-md hover:text-gray-900 text-olive-500 transition duration-300 focus:outline-none rounded hover:bg-gray-200 px-2 py-2">services</a> 
                <a href="/achievements" class="block py-1 text-md hover:text-gray-900 text-olive-500 transition duration-300 focus:outline-none rounded hover:bg-gray-200 px-2 py-2">achievements</a> 
                <a href="/careers" class="block py-1 text-md hover:text-gray-900 text-olive-500 transition duration-300 focus:outline-none rounded hover:bg-gray-200 px-2 py-2">careers</a>
                <a href="/dashboard" class="block py-1 text-md hover:text-gray-900 text-olive-500 transition duration-300 focus:outline-none rounded hover:bg-gray-200 px-2 py-2">dashboard</a>
                <a :href="route('login')" v-if="!$page.props.user" class="py-2 px-2 block rounded-full bg-olive-400 hover:bg-olive-600 text-white  shadow-lg shadow-sm transition duration-300">login</a>  
                <a :href="route('register')" v-if="!$page.props.user" class="py-2 px-2 block mt-1 rounded-full bg-olive-400 hover:bg-olive-600 text-white shadow-lg shadow-sm transition duration-300 mb-2">register</a>  
            </div>
        </nav>

	        <div class="splide__track">
                        <div class="lg:mr-20 lg:ml-20" id="images">
                            <img src="/images/img4.png" class="sm:w-full h-full">
                        </div>
	        </div>  

        <div class="flex justify-between" v-if="!$page.props.user">
           
            <div class="lg:absolute bottom-5 right-0 border-0 border-olive-500 p-5" style="background-color: #BAB2B5;">
                <a :href="route('register')" type="submit" class="w-full text-center font-bold rounded-full text-gray-100 hover:bg-blue-700 p-4 transition duration-700" style= "background-color: #123C69;">
                    Get Started!
                </a>
                <p class="text-white px-6 p-2 text-base" style="color: black;">Allow your passion to become your purpose.<br>And it will one day become your profit.</p>
            </div>
        </div>
              
</template>
<script>

    
    export default {
        props: {
            canLogin: Boolean,
            canRegister: Boolean,
            laravelVersion: String,
            phpVersion: String,
        },
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
       
   
  
      
    };
       
</script>
