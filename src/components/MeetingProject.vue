<template>
    <div class="full-control">
        <div class="list">
            <md-list :md-expand-single="expandSingle">
                <!-- md-list-item md-expand :md-expanded.sync="expandNews">
                    <md-icon>whatshot</md-icon>
                    <span class="md-list-item-text">News</span>

                    <md-list slot="md-expand">
                        <md-list-item class="md-inset">World</md-list-item>
                        <md-list-item class="md-inset">Europe</md-list-item>
                        <md-list-item class="md-inset">South America</md-list-item>
                    </md-list>
                </md-list-item>

                <md-list-item md-expand>
                    <md-icon>videogame_asset</md-icon>
                    <span class="md-list-item-text">Games</span>

                    <md-list slot="md-expand">
                        <md-list-item class="md-inset">Console</md-list-item>
                        <md-list-item class="md-inset">PC</md-list-item>
                        <md-list-item class="md-inset">Phone</md-list-item>
                    </md-list>
                </md-list-item>

                <md-list-item md-expand>
                    <md-icon>video_library</md-icon>
                    <span class="md-list-item-text">Video</span>

                    <md-list slot="md-expand">
                        <md-list-item class="md-inset">Humor</md-list-item>
                        <md-list-item class="md-inset">Music</md-list-item>
                        <md-list-item class="md-inset">Movies</md-list-item>
                        <md-list-item class="md-inset">TV Shows</md-list-item>
                    </md-list>
                </md-list-item -->

                <md-list-item md-expand>
                    <md-icon>shopping_basket</md-icon>
                    <span class="md-list-item-text">Projekte</span>

                    <md-list slot="md-expand">

                <md-list-item md-expand v-for="project in projects">
                    <span class="md-list-item-text"><b>{{ project.name }}</b></span>

                    <md-list slot="md-expand">
                        <md-list-item class="md-inset" v-for="meeting in project.meetings">{{
                            meeting.topic}} ({{meeting.dateTime}})
                        </md-list-item>
                    </md-list>
                </md-list-item>
                    </md-list>
                </md-list-item>

                <md-list-item md-expand>
                    <md-icon>mood</md-icon>
                    <span class="md-list-item-text">Pokemons</span>

                    <md-list slot="md-expand">
                        <md-list-item class="md-inset" v-for="pokemon in pokemons" v-bind:key="pokemon.name">
                            <a v-bind:href="pokemon.url" target="_blank">{{pokemon.name}}</a>
                        </md-list-item>
                    </md-list>
                </md-list-item>

                <!-- md-list-item>
                    <md-icon>chat_bubble_outline</md-icon>
                    <span class="md-list-item-text">Leer</span>
                </md-list-item -->
            </md-list>
        </div>
        <!-- div class="control">
            <md-switch v-model="expandSingle">Expand Only One</md-switch>
            <md-checkbox v-model="expandNews">Expand News</md-checkbox>
            <md-button class="md-raised md-primary" v-on:click.native="fillTable()">Fill Table</md-button>
            <md-button class="md-raised md-primary" v-on:click.native="clearTable()">Clear Table</md-button>
        </div -->
        <div class="details">
            <h1>Details</h1>
            <md-textarea v-bind="details"></md-textarea>
        </div>
        <div class="stepper">
            <md-steppers>
                <md-step id="first" md-label="First Step">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                </md-step>

                <md-step id="second" md-label="Second Step">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                </md-step>

                <md-step id="third" md-label="Third Step">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias doloribus eveniet quaerat modi cumque quos sed, temporibus nemo eius amet aliquid, illo minus blanditiis tempore, dolores voluptas dolore placeat nulla.</p>
                </md-step>
            </md-steppers>
        </div>
    </div>
</template>

<script>
    import axios from "axios";

    export default {
        name: 'MeetingProject',
        data: function () {
            return {
                expandNews: false,
                expandSingle: false,
                contacts: [],
                projects: [],
                pokemons: [],
                details: "Test"
            }
        },
        methods: {
            fillTable: function () {
                // this.contacts.push({firstName: 'Eron', lastName: 'Castro', email: 'eroncastro@test.com'});
                // this.contacts.push({firstName: 'Eron2', lastName: 'Castro', email: 'eroncastro2@test.com'});
                // this.contacts.push({firstName: 'Eron3', lastName: 'Castro', email: 'eroncastro3@test.com'});
                // console.log(contacts);

                this.projects.push(
                    {
                        id: "project123",
                        name: "reduce meetings",
                        manager: "Bob Builder",
                        meetings: [
                            {
                                id: "12345",
                                dateTime: "2019-05-14 17:15 UTC",
                                durationMin: 120,
                                topic: "no more meetings"
                            },
                            {
                                id: "12345",
                                dateTime: "2019-05-21 17:15 UTC",
                                durationMin: 120,
                                topic: "no more meetings"
                            }
                        ]
                    }
                );

                axios({method: "GET", "url": "https://pokeapi.co/api/v2/pokemon/?limit=151"}).then(result => {
                    this.pokemons = result.data.results;
                    console.log(result.data.count);
                }, error => {
                    console.error(error);
                });
            },
            clearTable: function () {
                this.contacts.splice(0, this.contacts.length);
                this.projects.splice(0, this.projects.length);
                this.pokemons.splice(0, this.pokemons.length);
            }
        },
        beforeMount() {
            this.fillTable()
        }
    }
</script>

<style lang="scss" scoped>
    $list-width: 400px;

    .full-control {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap-reverse;
    }

    .stepper {
        width: 100%;
    }

    .list {
        width: $list-width;
    }

    .full-control > .md-list {
        width: $list-width;
        max-width: 100%;
        height: 400px;
        display: inline-block;
        overflow: auto;
        border: 1px solid rgba(#000, .12);
        vertical-align: top;
    }

    .control {
        min-width: 250px;
        display: flex;
        flex-direction: column;
        padding: 16px;
    }
</style>
