<script lang="ts">
    import Loader from "../organisms/loader.organism.svelte";
    import type { ApiRef, ApiData } from "../organisms/loader.organism.svelte";
    import Nav from "../organisms/nav.organism.svelte";
    import Posts from "../organisms/posts.organism.svelte";
    import type { Tag } from "../molecules/tags.molecule.svelte";
    import type { PostData } from "../organisms/post.organism.svelte";
    import { getContext } from "svelte";
    import Image from "../molecules/image.molecule.svelte";

    const {tags, blogPosts, images} = getContext<ApiData>("api");
</script>

<Nav label="Luuk Meier" tagLabel="Filter: " tags={tags}/>
<Posts posts={blogPosts}/>


<style lang="scss">
    .img {
        grid-area: content;
    }
</style>
