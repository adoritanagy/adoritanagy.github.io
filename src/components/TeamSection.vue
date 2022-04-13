<template>
    <section id="team" class="team-section text-center py-12">
        <div class="max-width-section">
            <h2 class="mb-6">MEET THE SLOTHS</h2>
            <BaseDivider class="divider mb-12"/>
            <v-container fluid>
                <v-row justify="center">
                        <v-col 
                            v-for="(member, i) in team" 
                            :key="i"
                            cols="12" 
                            lg="2" 
                            sm="4"
                            xs="12"
                            align="top">
                            <TeamCard
                                class="team-card"
                                :imgSrc="member.imgSrc" 
                                :name="member.name" 
                                :description="member.description"/>
                        </v-col>
                </v-row>
            </v-container>
        </div>
    </section>
</template>
<script>
import TeamCard from "@/components/cards/TeamCard";
import BaseDivider from "@/components/BaseDivider";

export default {
    name:"TeamSection",
    components: {
        TeamCard,
        BaseDivider
    },
    data(){
        return {
            team: [
                {
                    name: "Paul",
                    description: "Community Manager",
                    imgSrc: "assets/paul.jpeg"
                },
                {
                    name: "Sergiu",
                    description: "Business Developer",
                    imgSrc: "assets/sergiu.jpg"
                },
                {
                    name: "Bogdan",
                    description: "Smart Contract Developer",
                    imgSrc: "assets/bogdan.jpg"
                },
                {
                    name: "Damaschin",
                    description: "Designer",
                    imgSrc: "assets/damaschin.jpg"
                },
                {
                    name: "Adorita",
                    description: "Developer",
                    imgSrc: "assets/adorita.png"
                }
            ]
        }
    }
}
</script>
<style lang="scss" scoped>
.team-section {
    background-color: #000000;

    .divider {
        max-width: 100px;
        margin-left: auto;
        margin-right: auto;
    }

    .max-width-section {
        margin: 0 auto;
        max-width: 100%;
        padding-left: 20px;
        padding-right: 20px;
    }

    .team-card {
        max-width: 250px;
        margin: 0 auto;
    }
}
</style>