<template>
    <div id="app">
        <div class="theme-container" :class="{'sidebar-open':iskq}">
            <header class="navbar">
                <div class="sidebar-button" @click="iskq=!iskq">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        aria-hidden="true"
                        role="img"
                        viewBox="0 0 448 512"
                        class="icon"
                    >
                        <path
                            fill="currentColor"
                            d="M436 124H12c-6.627 0-12-5.373-12-12V80c0-6.627 5.373-12 12-12h424c6.627 0 12 5.373 12 12v32c0 6.627-5.373 12-12 12zm0 160H12c-6.627 0-12-5.373-12-12v-32c0-6.627 5.373-12 12-12h424c6.627 0 12 5.373 12 12v32c0 6.627-5.373 12-12 12zm0 160H12c-6.627 0-12-5.373-12-12v-32c0-6.627 5.373-12 12-12h424c6.627 0 12 5.373 12 12v32c0 6.627-5.373 12-12 12z"
                        ></path>
                    </svg>
                </div>
            </header>
            <div class="sidebar-mask" @click="iskq=false"></div>
            <div class="sidebar"></div>
            <div class="page">
                <div class="content">
                    <h1 class="title">page</h1>
                </div>
            </div>
        </div>

        <router-view/>
    </div>
</template>
<script>



export default {
    data:function(){
        return{
            iskq:false
        }
    },
   created:function(){
       console.log(this.iskq) ;
       
   }
}
</script>


<style <style scoped>


body {
    color: #4a4a4a;
    font-size: 1em;
    font-weight: 400;
    line-height: 1.5;
}
.page {
    padding-left: 20rem;
}
.content:not(.custom) {
    max-width: 740px;
    margin: 0 auto;
    padding: 2rem 2.5rem;
}

@media (max-width: 959px) {
    .content:not(.custom) {
        padding: 2rem;
    }
}

@media (max-width: 419px) {
    .content:not(.custom) {
        padding: 1.5rem;
    }
}
.sidebar-mask {
    z-index: 9;
    width: 100vw;
    height: 100vh;
    /* opacity:0.4; */
    display: none;
}
.theme-container.sidebar-open .sidebar-mask {
    display: block
}

.sidebar {
    font-size: 15px;
    background-color: rgb(159, 199, 48);
    width: 20rem;
    position: fixed;
    z-index: 10;
    margin: 0;
    top: 3.6rem;
    left: 0;
    bottom: 0;
    box-sizing: border-box;
    border-right: 1px solid #eaecef;
    overflow-y: auto;
}
@media (max-width: 959px) {
    .sidebar {
        font-size: 15px;
        width: 16.4rem;
    }

    .page {
        padding-left: 16.4rem;
    }
}

@media (max-width: 719px) {
    .sidebar {
        top: 0;
        padding-top: 3.6rem;
        transform: translateX(-100%);
        transition: transform 0.2s ease;
    }

    .page {
        padding-left: 0;
    }

    .theme-container.sidebar-open .sidebar {
        transform: translateX(0);
    }

    .theme-container.no-navbar .sidebar {
        padding-top: 0;
    }
}
.sidebar-button {
    display: none;
    width: 1.25rem;
    height: 1.25rem;
    position: absolute;
    padding: .6rem;
    top: .6rem;
    left: 1rem
}

.sidebar-button .icon {
    display: block;
    width: 1.25rem;
    height: 1.25rem
}
@media (max-width: 719px) {
    .sidebar-button {
        display:block
    }
}
</style>
