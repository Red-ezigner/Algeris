<template>
    <div class="container">
        <footer class="py-3 my-4">
            <ul class="nav justify-content-center border-bottom pb-3 mb-3">
                <li class="nav-item"><a href="https://www.facebook.com/profile.php?id=100084241747600" class="nav-link facebook">Facebook</a></li>
                <li class="nav-item"><a href="https://www.instagram.com/red.esigner/" class="nav-link instagram">Instagram</a></li>
                <li class="nav-item"><a href="https://twitter.com/EsignerRed" class="nav-link twitter">Twitter</a></li>
                <li class="nav-item"><a href="https://www.youtube.com/channel/UCWasnWPMSb4vkvKIRYpFamQ" class="nav-link youtube">Youtube</a></li>
            </ul>
            <p class="text-center text-muted">© 2022 Company, Inc</p>
        </footer>
    </div>
</template>

<script>
    export default {
        name: 'Footer',
        props: {
            msg: String
        }
    }
</script>