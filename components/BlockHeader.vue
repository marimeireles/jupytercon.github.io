<template>
    <div class="main">
        <MenuBar class='menubar'/>
        <div class="top">
            <div class="page-title float-left">
                <h1><span>{{title}}</span><br/><span class="subtitle">{{subtitle}}</span></h1>
            </div>
            <div class="side-content float-left">
                <slot name="side-content">
                <div>
                    <span class="grey">Berlin, Germany <br/></span>
                    <span class="orange">10-11 August: Tutorials <br/>
                        12-13 August: Conference <br/>
                        14 August: Sprints
                    </span>
                </div>
                </slot>
            </div>
        </div>
        <div class="background">
            <div :class="tall ? 'content-tall' : 'content'">
                <slot name="content">
                    <div class="tickets" v-if="buttons">
                        <div><a class="button hollow">Buy tickets</a></div>
                        <div><a class="button hollow">Submit a talk</a></div>
                    </div>
                </slot>
            </div>
            <img src="~assets/svg/circle-dashed-orange.svg" class="halfcircle" v-if="!tall"/>
            <div class="movie">
                <slot name="media">
                    <video class="autoplay" id="autoplay-video" autoplay="false" muted="true" loop="" style="height: 516px;">
                        <source src="https://ak8.picdn.net/shutterstock/videos/7925128/preview/stock-footage-berlin-nov-timelpase-view-of-the-berlin-tv-tower-and-skyline-one-of-the-citys-main-tourist.mp4"
                            type="video/mp4"/>
                    </video>
                </slot>
            </div>
        </div>
    </div>        
</template>


<script>
    import MenuBar from "../components/MenuBar";
    export default {
        name: "BlockHeader",
        components: {MenuBar},
        props: {
            title: {
                type: String,
                default: 'Untitled'
            },
            subtitle: {
                type: String,
                default: null
            },
            buttons: {
                type: Boolean,
                default: true,
            },
            tall: {
                type: Boolean,
                default: false,
            },
        },
    }
</script>

<style scoped lang="scss">
    @import 'assets/scss/settings';
    .menubar {
        position: relative;
        z-index: 1;
    }
    .main {
        position: relative;
        background-color: white;
        width: 100%;
        height: 100%;
        height: 800px;
        .top {
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            right: 0;
            margin-left: 120px;
            height: 284px;
            .page-title {
                width: 60%;
                margin-top: 110px;
                color: $figma-orange;
                h1 {
                    line-height: 100%;
                }
                .subtitle {
                    margin-top: -30px;
                    color: $figma-grey2;
                }
            }
            .side-content {
                z-index: -1;
                background-color: $figma-grey3;
                padding-top: 140px;
                padding-left: 30px;
                width: 40%;
                height: 100%;
                div {
                    font-size: 24px;
                    line-height: 31px;
                    font-family: $figma-font-gosha;

                    .grey {
                        color: $figma-grey;
                        font-family: $figma-font-ibm;
                        position: relative;
                        top: 2px;
                    }

                    .orange {
                        color: $figma-orange
                    }
                }
            }

        }
        .background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 800px;
            overflow: hidden;
            .content {
                position: absolute;
                background-color: $figma-orange;
                height: 212px;
                width: 541px;
                left: 0px;
                bottom: 0px;
                .tickets {
                    color: white;
                    margin-left: 250px;
                    margin-top: 50px;
                    .button {
                        color: white;
                        border-color: white;
                        width: 210px;
                    }

                }
            }
            .content-tall {
                position: absolute;
                background-color: $figma-orange;
                height: 434px;
                width: 541px;
                left: 0px;
                bottom: 0px;
            }
            .halfcircle {
                position: absolute;
                bottom: 0px;
                left: 0;
            }
            .movie {
                position: absolute;
                left: 541px;
                top: 284px;
                bottom: 0px;
                right: 0px;
                video, img {
                    height: 516px;
                    object-fit: cover;
                    width: 100%;

                }

            }
        }
    }

</style>