<script>
    import Introduction from './Introduction.svelte';
    import Skills from './Skills.svelte';
    import Experience from './Experience.svelte';
    import Hobbies from './Hobbies.svelte';
    import Label from './Label.svelte';
</script>

<main class="max-w-[1200px] mx-auto px-6 py-6">
    <Label>// introductie</Label>
    <Introduction />

    <Label>// skills & tech stack</Label>
    <Skills />

    <Label>// werkervaring</Label>
    <Experience />

    <Label>// hobbies</Label>
    <Hobbies />

    <Label>// contact</Label>
</main>
