<template>
    <div class="has-text-centered animated fadeInDown">
        <div id="reaction-role-container">
            <img src="/static/favicon/favicon.png"
                height="256"
                width="256"
                class="reaction-role">
            <h1 class="title">Reaction Role</h1>
            <h2 class="subtitle">
                Clean role management using reactions!
                Users may join/leave roles just by reacting.
            </h2>
            <div id="action_buttons">
                <a id="invite_btn"
                    href="https://discordapp.com/oauth2/authorize?client_id=441751906428256277&permissions=8&scope=bot"
                    target="_blank" class="button is-info is-large">
                    <b-icon icon="robot"></b-icon>
                    <span>Invite To Server</span>
                </a>
                <router-link id="doc_btn"
                    to="/Documentation"
                    class="button is-large is-outlined is-warning">
                        <b-icon icon="file-alt" pack="far"></b-icon>
                    <span>View Docs</span>
                </router-link>
            </div>
        </div>
        <div class="columns">
            <div class="column is-7 container sponsor has-text-centered">
                <h1 class="title">Patreon Supporters</h1>
                <p class="sponsor-desc is-size-5">
                    Through donations, and sponsorship, you allow Reaction Role to blossom.
                    Your donation contributes directly to the hosting cost,
                    and the development effort.
                </p>
                <!-- <h2 class="title sponsor-title">Sponsor</h2>
                <div>
                    <a href="SPONSOR_LINK" target="_blank" title="Tuxedo Gaming">
                        <img src="~@/assets/img/sponsor.png" class="sponsor-asset">
                    </a>
                </div> -->
                <h2 class="title sponsor-title">Patrons</h2>
                <div class="columns is-multiline">
                    <div class="column is-1" v-for="Patron in Patrons" :key="Patron.id">
                        <b-tooltip :label="Patron.name">
                            <img v-lazy="Patron.avatar" class="patron" :alt="Patron.name">
                        </b-tooltip>
                    </div>
                </div>
                <a href="https://www.patreon.com/RumbleFrog" target="_blank">
                    <img src="/static/img/become_a_patron_button.png">
                </a>
            </div>
        </div>
    </div>
</template>

<script>
import Patrons from '@/assets/data/Patrons.json';

export default {
    name: 'Home',
    data() {
        return {
            Patrons,
        };
    },
};
</script>

<style scoped>
.reaction-role {
    -webkit-animation: mover 1.5s infinite alternate;
    animation: mover 1.5s infinite alternate;
}
#reaction-role-container {
    margin-top: 20vh;
    margin-bottom: 10vh;
}
@-webkit-keyframes mover {
    0% { transform: translateY(0); }
    100% { transform: translateY(-30px); }
}
@keyframes mover {
    0% { transform: translateY(0); }
    100% { transform: translateY(-30px); }
}
.sponsor-title {
    margin: 1.5em 0 1em;
    font-size: 2rem;
}
.sponsor-desc {
    margin-bottom: 1em;
}
.sponsor {
    padding: 5em 1em;
}
.sponsor-asset {
    border-radius: 50%;
    border: 2px solid #FF2B56;
}
.patron {
    width: 45px;
    height: 45px;
    min-width: 45px;
    border-radius: 50%;
    border: 2px solid #70ca0a;
}
</style>

