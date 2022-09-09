<template>
    <div class="container">
        <header class="container d-flex flex-wrap justify-content-center py-3 mb-4 border-bottom">
            <a href="/" class="d-flex align-items-center mb-3 mb-md-0 me-md-auto text-dark text-decoration-none">
                <svg class="bi me-2" width="40" height="32"><use xlink:href="#bootstrap"></use></svg>
                <span class="fs-4">RedeZigner</span>
            </a>
                
            <ul class="nav nav-pills">
                <li class="nav-item"><a href="https://www.facebook.com/profile.php?id=100084241747600" class="nav-link facebook">Facebook</a></li>
                <li class="nav-item"><a href="https://www.instagram.com/red.esigner/" class="nav-link instagram">Instagram</a></li>
                <li class="nav-item"><a href="https://twitter.com/EsignerRed" class="nav-link twitter">Twitter</a></li>
                <li class="nav-item"><a href="https://www.youtube.com/channel/UCWasnWPMSb4vkvKIRYpFamQ" class="nav-link youtube">Youtube</a></li>
            </ul>
        </header>
    </div>
</template>


<script>
    export default {
        name: 'HelloWorld',
        props: {
            msg: String
        }
    }
</script>

<style>
    .twitter{
        color: #1da1f2 !important;
    }
    .facebook{
        color: #1877f2 !important;
    }
    .youtube{
        color: #ff0000 !important;
    }
    .instagram{
        color: #c32aa3 !important;
    }
</style>