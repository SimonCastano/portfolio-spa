<script setup>
import { Head, Link } from "@inertiajs/vue3";
import JetApplicationMark from "@/components/ApplicationMark.vue";
import PrimaryButton from "@/components/PrimaryButton.vue";
import Section from "@/components/Section.vue";
import Skill from "@/components/Skill.vue";

import { defineComponent } from "vue";

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    skills:Object ,
});


</script>

<template>
    <Head title="Simon welcome" />
    <div
        class="grid grid-cols-2 text-right py-10 px-72 bg-gray-800 text-gray-200"
    >
        <div>
            <JetApplicationMark class="h-12" />
        </div>
        <div v-if="canLogin">
            <Link
                v-if="$page.props.user"
                :href="route('dashboard')"
                class="text-sm underline"
                >Dashboard</Link
            >

            <template v-else>
                <Link :href="route('dashboard')" class="text-base underline"
                    >Login</Link
                >
                <Link
                    v-if="canRegister"
                    :href="route('dashboard')"
                    class="textbase underline place-self-end ml-4"
                    >Register
                </Link>
            </template>
        </div>
    </div>

    <header class="bg-gray-800 pt-16 h-screen px-72 flex-column">
        <div class="  p-6  text-blue-100 border-b-2">
            <h1 class="text-5xl font-black">Hey This is Simon</h1>
            <p>
                Software Engineer, developer and designer I would like to work
                with you
            </p>
        </div>
        <div class="flex items-end border-b-2 border-gray-500 pb-2 pt-72 w-96">
            <p class="text-gray-200 font-bold mr-2 text-xl">
                Want to know more?
            </p>
            <PrimaryButton
                class="bg-green-400  rounded font-bold text-sm text-gray-800 hover:bg-green-500"
                >Contact with me
            </PrimaryButton>
        </div>
        <div class="text-gray-300 mt-3 animate-pulse text-center text-9xl pt-10 ">
            <a href="#skills" >&#8675;</a>
        </div>
    </header>
    <Section id="skills" class=" bg-gray-200 text-blue-800 h-screen">
        <h2 class="text-2xl font-black">Skills</h2>
        <div class="grid grid-cols-2">
            <div  v-for="skill in skills">
                <Skill  :background="skill.color">
                    {{ skill.name }}
                </Skill>
            </div>
        </div>
        <div class="text-center">
            <PrimaryButton
            class="bg-indigo-600  rounded font-bold text-sm text-gray-800 hover:bg-indigo-800"
            > Get in touch
        </PrimaryButton>
    </div>
        
    </Section>
    <Section class="bg-gray-100 text-blue-800 h-screen">
        <h2 class="text-2xl font-black">Projects</h2>
        <div class="text-center">

            <PrimaryButton
            class="bg-purple-700  rounded font-bold text-sm  hover:bg-purple-800"
            > Lets's chat
        </PrimaryButton>
    </div>
    </Section>

    <Section class="flex justify-between bg-gray-800 text-xl text-gray-200">
        <p>All rigths reserved &copy; Simón Castaño R.</p>
        <ul class="flex justify-evenly items-center gap-10">
            <li> <Link target="_blank" class="border-b p-1 px-2 hover:text-indigo-300" href="#"> Github</Link></li>
            <li> <Link target="_blank" class="border-b p-1 px-2 hover:text-indigo-300" href="#"> Behance</Link></li>
            <li> <Link target="_blank" class="border-b p-1 px-2 hover:text-indigo-300" href="#"> Linkedin</Link></li>
            <li> <Link target="_blank" class="border-b p-1 px-2 hover:text-indigo-300" href="#"> Youtube</Link></li>
            <li> <Link target="_blank" class="border-b p-1 px-2 hover:text-indigo-300" href="#"> Twitter</Link></li>
            
        </ul>
    </Section>
</template>
