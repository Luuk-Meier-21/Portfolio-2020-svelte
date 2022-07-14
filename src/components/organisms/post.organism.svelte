<script lang="ts" context="module">
    import type { Tag } from "../molecules/tags.molecule.svelte";
    import type { ImageData } from "../molecules/image.molecule.svelte";

    export interface ParagraphData {
        typeName: "PARAGRAPH";
        paragraphType: string;
        content: {
            text: string;
        }
    }

    type ContentData = ImageData | ParagraphData;

    export interface PostData {
        slug: string;
        title: string;
        tags: Tag[];
        content: ContentData[];
    };
</script>

<script lang="ts">
    import Image from "../molecules/image.molecule.svelte";

    export let post: PostData;
</script>

<h1 class="title">{post.title}</h1>
<div class="content">
    {#each post.content as item}
    {#if item.typeName === "PARAGRAPH" } <!-- Paragraph -->
       <p>{item.content.text}</p>
    {/if}
    {#if item.typeName === "IMAGE" } <!-- Paragraph -->
        <Image src={item.image.url} alt={item.alt} caption={item.caption}></Image>
    {/if}
{/each}
</div>

<style lang="scss">
    .title {
        grid-area: title;
    }

    .content {
        grid-area: content;
    }
</style>
