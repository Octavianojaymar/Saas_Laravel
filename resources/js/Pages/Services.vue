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
                       <img src="/images/Saas logo.png" alt="" class="h-5 w-5" style= "width: 100px; height: 100px">
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
    <div >
	        <div class="splide__track">
		        <ul class="splide__list">

                        <div class="text-lg-center font-semibold bg-sepia-300 py-5 px-5 lg:ml-10 lg:mr-10 rounded mt-20" style="text: align-center; width: 1285px; background-color: #EDC7B7">
                            <p class="">Guidance Counseling offers the following services:
                            <br><br>1. Psychological Test - Used of tests to quantify students psychophysical behaviour, abilities and problems and to make predictions about psychological performance.
                            <br><br>2. Referral Counseling - Referral Counseling service make recommendations of whereelse might take treatment. This may happen if counselors cannot accept the students for some reason or if after some treatment has occured, the students needs have change.
                            <br><br>3. Exit Interview - The graduating students are given an opportunity to discuss their future plans, career choices, and various options for employment.
                            <br><br>4. Counseling Services - It aims to assists students in their emotional, social, physical, spiritual, and  cognitive needs. <br>
                             During this pandemic the University guidance center offers online counseling so that the guidance counselors can reach out to students easier and use the online platform to cater their personal issues problems and concerns.</p>
                        </div>
		        </ul>
	        </div>  
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