<script lang="ts" context="module">
    export interface ImageData {
        typeName: "IMAGE"
        imageType: string;
        image: {
            url: string;
        }
        alt: string;
        caption: string;
    }
</script>

<script lang="ts">
    type ImageType = "default" | "landscape" | "portrait";

    export let src: string;
    export let alt: string;
    export let caption: string;

    export let type: ImageType = "default";

</script>

<figure class="image">
    <img class="image__source" src={src} alt={alt}>
    <figcaption class="image__caption is--small">{caption}</figcaption>
</figure>

<style lang="scss">
    .image {
        display: grid;
        width: 100%;
        margin-bottom: var(--single);
 
        &__source {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        &__caption {
            
        }
    }
</style>