<script>
    export default {
        data() {
            return {
                navNames: [
                    {
                        name: "CHARACTER",
                        isActive: true,
                    },
                    {
                        name: "COMICS",
                        isActive: false,
                    },
                    {
                        name: "MOVIES",
                        isActive: false,
                    },
                    {
                        name: "TV",
                        isActive: false,
                    },
                    {
                        name: "GAMES",
                        isActive: false,
                    },
                    {
                        name: "COLLECTIBLES",
                        isActive: false,
                    },
                    {
                        name: "VIDEO",
                        isActive: false,
                    },
                    {
                        name: "FAN",
                        isActive: false,
                    },
                    {
                        name: "NEWS",
                        isActive: false,
                    },
                    {
                        name: "SHOP",
                        isActive: false,
                    }
                ],
                activeIndex: 0,
            }
        },
        methods: {
            changeActive: function(index) {
                if (this.activeIndex != index) {
                    this.navNames[this.activeIndex].isActive = false;
                    this.navNames[index].isActive = true;
                    this.activeIndex = index;
                }
            }
        }
    }
</script>

<template>
    <header class="container">
        <div>
            <img src="../assets/img/dc-logo.png" alt="DC Logo">
        </div>
        <ul>
            <li v-for="(names, index) in navNames" :key="index" @click="changeActive(index)"  :class="{ active: names.isActive }" > 
                <a href="">{{ names.name }}</a>
            </li>
        </ul>
    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

    header {
        @include flex(space-between);

        img {
            padding: 20px;
        }

        ul {
            display: flex;

            li {
                display: flex;
                align-items: center;
                list-style: none;
                padding: 0 5px;
                

                a {
                    text-decoration: none;
                    color: black;
                }

                &:hover {
                    border-bottom: 5px solid $primary;
                    padding-top: 5px;
                    a {
                        color: $primary;
                    }
                }
                &.active {
                    border-bottom: 5px solid $primary;
                    padding-top: 5px;
                    a {
                        color: $primary;
                    }
                    
                }
            }

            
        }
        
    }
    
</style>
