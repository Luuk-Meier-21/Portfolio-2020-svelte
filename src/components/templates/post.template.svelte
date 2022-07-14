<script lang="ts">
    import { getContext } from "svelte";
    import Nav from "../organisms/nav.organism.svelte";
    import Post from "../organisms/post.organism.svelte";
    import NotFound from "./not-found.template.svelte";
    import type { PostData } from "../organisms/post.organism.svelte";

    export let postSlug: string;

    const { blogPostBs } = getContext("api");
    console.log(blogPostBs)
    $: currPost = blogPostBs.find((post) => post.slug == postSlug);
    $: isFound = currPost !== undefined;
</script>

{#if isFound}
    <Nav label="Luuk Meier" tags={currPost.tags}/>
    <Post post={currPost}/>
{/if}

{#if !isFound} <NotFound/> {/if}

<style lang="scss">
    
</style>
