<template>
    <div>
        <div class="p-6 sm:px-5 bg-sepia-100 border-b border-sepia-300" style="background-color: #AC3B61">
            <div class="flex items-center text-gray-800">
                <jet-application-logo class="block h-12 w-auto" /> 
                <div class="text-xl flex " style="color: white">
                         Hello! Welcome to Guidance Counseling :)
                </div>      
            </div>
            
            
        </div>
        <div class=""  style="background-color: #EDB5BF">
            <div class="p-6 ">
                <div class="ml-4 text-md text-black leading-7 font-semibold"> 
                    <div class="">
                        <div >
                            <a href="/" class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                                    <path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z" />
                                </svg>
                                <span class="ml-1">
                                    Home
                                </span>
                            
                            </a>
                        </div>
                    </div>
                    
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import JetApplicationLogo from '@/Jetstream/ApplicationLogo'

    export default {
        components: {
            JetApplicationLogo,
        },
    }
</script>
