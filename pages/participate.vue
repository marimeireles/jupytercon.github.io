<template>
    <div>
        <BlockHeader :buttons="false" title="Participate" tall>
            <template v-slot:media>
                <img src="~assets/images/participate.jpg"/>
            </template>
            <template v-slot:content>
                <div class="header-content">
                    <h2>Get involved</h2>
                    <slot>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Turpis risus fames dolor volutpat risus vitae.
                        Malesuada elit nec nibh elementum at faucibus nisl. Scelerisque elit, vel cursus scelerisque. Sed ut
                        malesuada pretium faucibus odio quis
                        congue.</p>
                    </slot>
                </div>

            </template>
        </BlockHeader>
        <div class="tickets">
            <h1>Tickets</h1>
        </div>

        <BlockGreyOrange>
            <div class="proposals">
                <h1>Proposals</h1>
                <div class="grid-x grid-padding-x">
                    <div class="cell small-12 medium-4">
                        <h2>Talks</h2>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Turpis risus fames dolor volutpat risus vitae.
                            Malesuada elit nec nibh elementum at faucibus nisl. Scelerisque elit, vel cursus scelerisque. Sed ut
                            malesuada pretium faucibus odio quis
                            congue.</p>
                    </div>
                    <div class="cell small-12 medium-4">
                        <h2>Tutorials</h2>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Turpis risus fames dolor volutpat risus vitae.
                            Malesuada elit nec nibh elementum at faucibus nisl. Scelerisque elit, vel cursus scelerisque. Sed ut
                            malesuada pretium faucibus odio quis
                            congue.</p>
                    </div>
                    <div class="cell small-12 medium-4">
                        <h2>Sprints</h2>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Turpis risus fames dolor volutpat risus vitae.
                            Malesuada elit nec nibh elementum at faucibus nisl. Scelerisque elit, vel cursus scelerisque. Sed ut
                            malesuada pretium faucibus odio quis
                            congue.</p>
                        <a class="button hollow">Propose a sprint</a>
                    </div>
                </div>
            </div>
        </BlockGreyOrange>
    </div>
</template>

<script>
    import BlockHeader from "../components/BlockHeader";
    import BlockAbout from "../components/BlockAbout";
    import BlockGreyOrange from "../components/BlockGreyOrange";

    export default {
        name: "participate",
        components: {BlockHeader, BlockAbout, BlockGreyOrange},
    }
</script>

<style lang="scss" scoped>
    @import 'assets/scss/settings';
    .location-name {
        color: $figma-orange;
    }
    .header-content {
        margin: 100px 120px;
        color: white;
        h2 {
            font-size: 30px;
        }
    }
    .tickets {
        height: 800px;
        padding: 100px 120px;
        background-color: white;
        h1 {
            color: $figma-orange;
        }
    }
    .proposals {
         margin-top: -100px; // correct default margin
         h1 {
             margin-bottom: 100px;
         }
    }
</style>
