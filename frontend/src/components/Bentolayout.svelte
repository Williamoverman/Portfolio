<script>
    import Introduction from './Introduction.svelte';
    import Skills from './Skills.svelte';
    import Experience from './Experience.svelte';
    import Hobbies from './Hobbies.svelte';
    import Contact from './Contact.svelte';
    import Label from './Label.svelte';
</script>

<main class="max-w-[1200px] mx-auto px-6 py-6">
    <Label id="over">// introductie</Label>
    <Introduction />

    <Label id="skills">// skills & tech stack</Label>
    <Skills />

    <Label id="experience">// werkervaring</Label>
    <Experience />

    <Label id="hobbies">// hobbies</Label>
    <Hobbies />

    <Label id="contact">// contact</Label>
    <Contact />  
</main>