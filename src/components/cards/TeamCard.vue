<template>
    <div class="team-card">
        <v-img
            max-width="250px"
            :src="require(`@/${imgSrc}`)"
            class="team-card__image mb-2"
        >
            <template v-slot:placeholder>
                <v-row
                    class="fill-height ma-0"
                    align="center"
                    width="250"
                    justify="center"
                >
                    <v-progress-circular
                    indeterminate
                    color="grey lighten-5"
                    ></v-progress-circular>
                </v-row>
        </template>
        </v-img>
        <h3>{{name}}</h3>
        <p>{{description}}</p>
    </div>
</template>
<script>
export default {
    name: "TeamCard",
    props: {
        imgSrc: {
            type: String,
            required: true
        },
        name: {
            type: String,
            required: true
        },
        description: {
            type: String,
            default: "" 
        }
    }
}
</script>
<style lang="scss" scoped>
.team-card {
    text-align: center;
    h3 {
        color: #f7c21a;
    }
    .team-card__image {
        border-radius: 4px;
    }
}
</style>