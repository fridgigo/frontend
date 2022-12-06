<template>
    <div class="d-flex justify-content-center align-items-center flex-column mt-5">
        <mainButton className="btn btn-outline-success p-2 pl-3 pr-3 mb-2" link="/" title="Homepage" linkClassName="link-green" />
        <img src="./../static/images/404.gif" class="img-fluid" alt="404 Page not found :(">
    </div>
</template>

<script>
import mainButton from '../components/buttons/main-button.vue';
export default {
    name: "Error",
    head: {
        title: "fridgiGO | Page not found"
    },
    components: {
        mainButton
    }
}
</script>