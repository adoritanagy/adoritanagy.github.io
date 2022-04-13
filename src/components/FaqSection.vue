<template>
    <section id="faq" class="faq-section py-12">
        <div class="max-width-section">
            <h2 class="text-center mb-6">FAQ</h2>
            <BaseDivider class="divider mb-12"/>
            <v-expansion-panels dark>
                <v-expansion-panel
                    v-for="(item,i) in items"
                    :key="i"
                >
                <v-expansion-panel-header>
                    {{item.header}}
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                    {{item.content}}
                </v-expansion-panel-content>
                </v-expansion-panel>
            </v-expansion-panels>
        </div>
    </section>
</template>
<script>
import BaseDivider from "@/components/BaseDivider";

export default {
    name: "FaqSection",
    components: {
        BaseDivider
    },
    data(){
        return {
            items: [
                {
                    header: "What is Urban Sloth’s ?",
                    content: "The cuddly and sluggish creatures that populate the Elrond blockchain, Their teeny-tiny faces suggest mischief, as if they could pull off the mother of all pranks or make one heck of a dirty joke if they had the energy."
                },
                {
                    header: "How many Urban Sloth’s are out there ?",
                    content: "They're a collection of 5000 unique NFTS generated at random from more than 100+ hand-drawn traits by our artist."
                },
                {
                    header: "What  is the utility and benefits of holding a Sloth ?",
                    content: "You'll have complete control as a holder. You and the team will have the opportunity to create the future of Urban Sloths because everything in this community will be voted on by the holders. Of course, you will be rewarded for your efforts."
                },
                {
                    header: "The first 1000 ?",
                    content: "The early settlers will be the foundation for future generations; their contributions will be remembered, and they will be entitled to special and unique benefits."
                }
            ]
        }
    }
}
</script>
<style lang="scss">
.faq-section {
    .v-expansion-panels .v-expansion-panel {
        background-color: #000000 !important;
    }

    background-color: #000000;

    .divider {
        max-width: 100px;
        margin-left: auto;
        margin-right: auto;
    }

    .max-width-section {
        margin: 0 auto;
        max-width: 1000px;
        padding-left: 20px;
        padding-right: 20px;
    }
}
</style>