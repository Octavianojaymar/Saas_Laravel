<template>
 <nav class="">
        <div class="max-w-7xl mx-auto">
            <div class="flex justify-between">
                <div class="flex">  
                    <div>
                        <a href="/" class="flex items-center text-olive-500 hover:text-olive-600 py-4 px-3 transition duration-300">
                            <path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z" />
                            <img src="/images/Saas logo.png" alt="" class="h-5 w-5" style= "width: 100px; height: 100px">
                            <span class="text-xl font-bold" style="color: black">
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
                        <a :href="route('register')" class="rounded-full bg-olive-400 hover:bg-olive-600 text-white px-6 p-2 shadow-lg shadow-sm transition duration-300" style="color: black; background-color: #9FEDD7">register</a>  
                    </div>
                </div>
                <div class="lg:hidden flex items-center" >
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
            <a :href="route('register')" class="py-2 px-2 block mt-1 rounded-full bg-olive-400 hover:bg-olive-600 text-white shadow-lg shadow-sm transition duration-300 mb-2">register</a>  
        </div>
    </nav>
    <jet-authentication-card style="background-color:#AC3B61">    
        <template #logo>
            <jet-authentication-card-logo/>
        </template>
        <div style ="background-color:#EDC7B7" >
        <jet-validation-errors class="mb-4" />

        <div v-if="status" class="mb-4 font-medium text-sm text-green-600">
            {{ status }}
        </div>

        <form @submit.prevent="submit"> 
            
            <div>
                <jet-label for="email" value="Email" />
                <jet-input id="email" type="email" class="mt-1 block w-full" v-model="form.email" required autofocus />
            </div>

            <div class="mt-4">
                <jet-label for="password" value="Password" />
                <jet-input id="password" type="password" class="mt-1 block w-full" v-model="form.password" required autocomplete="current-password" />
            </div>

            <div class="block mt-4">
                <label class="flex items-center">
                    <jet-checkbox name="remember" v-model:checked="form.remember" />
                    <span class="ml-2 text-sm text-gray-600">Remember me</span>
                </label>
            </div>

            <div class="flex items-center justify-end mt-4">
                <inertia-link v-if="canResetPassword" :href="route('password.request')" class="underline text-sm text-gray-600 hover:text-gray-900">
                    Forgot your password?
                </inertia-link>

                <jet-button class="ml-4" style="background-color: #9FEDD7; color: black" :class="{ 'opacity-25': form.processing }" :disabled="form.processing">
                    Log in
                </jet-button>
            </div>
            
        </form>
        </div>
    </jet-authentication-card>
</template>

<script>
    import JetAuthenticationCard from '@/Jetstream/AuthenticationCard'
    import JetAuthenticationCardLogo from '@/Jetstream/AuthenticationCardLogo'
    import JetButton from '@/Jetstream/Button'
    import JetInput from '@/Jetstream/Input'
    import JetCheckbox from '@/Jetstream/Checkbox'
    import JetLabel from '@/Jetstream/Label'
    import JetValidationErrors from '@/Jetstream/ValidationErrors'

    export default {
        components: {
            JetAuthenticationCard,
            JetAuthenticationCardLogo,
            JetButton,
            JetInput,
            JetCheckbox,
            JetLabel,
            JetValidationErrors
        },

        props: {
            canResetPassword: Boolean,
            status: String
        },

        data() {
            return {
                form: this.$inertia.form({
                    email: '',
                    password: '',
                    remember: false
                })
            }
        },

        methods: {
            submit() {
                this.form
                    .transform(data => ({
                        ... data,
                        remember: this.form.remember ? 'on' : ''
                    }))
                    .post(this.route('login'), {
                        onFinish: () => this.form.reset('password'),
                    })
            }
        },
        mounted(){
            const btn = document.querySelector('button.mobile-menu-button')
            const menu = document.querySelector('.mobile-menu')
            btn.addEventListener("click",()=>{
            menu.classList.toggle("hidden");
            });
        }
    }
</script>
