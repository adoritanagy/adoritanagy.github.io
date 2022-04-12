<template>
    <section class="team-section text-center py-12">
        <h2 class="mb-12">MEET THE SLOTHS</h2>
        <div class="d-flex align-center justify-center">
            <TeamCard 
                v-for="(member, i) in team" 
                :key="i" 
                :imgSrc="member.imgSrc" 
                :name="member.name" 
                :description="member.description"/>
        </div>
    </section>
</template>
<script>
import TeamCard from "@/components/cards/TeamCard";

export default {
    name:"TeamSection",
    components: {
        TeamCard
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
}
</style>