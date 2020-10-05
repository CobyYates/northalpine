<template>
    <v-container fluid>
        <v-row class="mb-12">
            <v-col cols="12" sm="12" md="4" lg="3" xl="3" class="d-flex justify-center align-center">
                <v-img
                    src="https://scontent-den4-1.cdninstagram.com/v/t51.2885-19/s150x150/81616161_778193966008210_792081334766927872_n.jpg?_nc_ht=scontent-den4-1.cdninstagram.com&_nc_ohc=cgjQs0w-xMQAX9oTJZ3&oh=2da47f49e431a196851c66489c8d7c15&oe=5FA51C51"
                    max-width="300"
                ></v-img>
            </v-col>
            <v-col cols="12" sm="12" md="8" lg="9" xl="9" class="d-flex justify-center align-center">
                {{about}}
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    data() {
        return {
            about: 'Suspendisse vel egestas risus, sed convallis ante. Vestibulum blandit hendrerit urna eget euismod. Aenean aliquam lectus nisi, eu malesuada nulla dapibus vitae. Aliquam erat volutpat. Donec placerat mollis turpis nec pellentesque. Nunc urna eros, rhoncus id sem et, accumsan efficitur tellus. Fusce efficitur enim ligula, volutpat maximus arcu porta in. Curabitur ac fermentum lectus, et consequat magna. Maecenas dapibus est a ipsum tincidunt, a malesuada magna feugiat. Proin laoreet magna vel nulla mattis malesuada. Curabitur vitae nisl sed odio vestibulum ullamcorper non fringilla metus. Cras bibendum turpis et lectus congue pellentesque. Etiam ac lectus vitae sem bibendum consectetur sit amet vitae nulla.'
        }
    }
}
</script>

<style>

</style>