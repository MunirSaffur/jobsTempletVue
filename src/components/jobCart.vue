<template>
    <div>
<b-col class="mt-2 mb-2">
     <b-card 
     :title="name"
     img-src="https://media.istockphoto.com/photos/heart-shape-paper-book-on-the-beach-picture-id817147678?k=6&m=817147678&s=612x612&w=0&h=vNJJJoRPaieom61bMwQxaGtOImMhJsoxz1OIgLZNOEw="
     style="max-width:20rem"
     calss="mb"
     >
       <b-card-text>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque id tenetur minima aut eveniet, necessitatibus numquam doloremque provident molestiae exercitationem? Alias nulla consectetur esse dignissimos aliquam vero omnis, quidem animi!</b-card-text>
       <b-button variant="primary">Applay</b-button>
     </b-card>
   </b-col>
    </div>
</template>

<script>

export default {
    name: 'jobcart',
    props: ["name"]
}
</script>

<style lang="scss" scoped>

</style>