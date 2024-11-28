<script lang="ts">
    import { page } from "$app/stores";
</script>

<div class="container">
    <h1>{$page.status}</h1>
    <p>{$page.error?.message}</p>
    <p class="link"><a href="/">go back home?</a></p>
</div>

<style lang="scss">
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100%;
        text-align: center;

        .link {
            margin-top: 0.5rem;
            font-size: 1rem;
        }
    }
</style>