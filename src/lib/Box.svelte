<script>
    import { scale } from 'svelte/transition';

    export let user = {
        username: 'MExample',
        tag: 1234,
        bannerColor: '#063DF1',
        profilePictureUrl: 'https://cdn.discordapp.com/avatars/282861813215789058/5d1277d788ff2ed8f86315b39e1705b7.png?size=256',
    }

    // for (let [prop, value] of Object.entries(user)) {
    //     let varString = `--theme-${prop}`
    //     document.documentElement.style.setProperty(varString, value)
    // }

    // Set CSS var for banner background color
    document.documentElement.style.setProperty('--banner-color', user.bannerColor)
</script>

<div class="card" in:scale out:scale>
    <header>
        <div class="banner"></div>
        <div class="pfp">
            <!-- svelte-ignore a11y-img-redundant-alt -->
            <img src={user.profilePictureUrl} alt="profile picture">
        </div>
        <h2 id="username">{user.username}<span>#{user.tag}</span></h2>
    </header>
</div>

<style>
    :root {
        --background-color: #18191c
    }

    * {
        box-sizing: border-box;
    }

    .card {
        background-color: var(--background-color);

        position:  absolute;
        top:       50vh;
        left:      50vw;
        transform: translate(-50%, -50%);

        width:     600px;
        height:    536px;
        z-index:   2137;
    }

    header {
        height: 235px;
    }

    .banner {
        width: 100%;
        height: 120px;
        background-color: var(--banner-color);
        border-top-left-radius: 8px;
        border-top-right-radius: 8px;
    }

    .pfp {
        position: relative;
        top: calc(-135px / 2);
        left: 15px;
        width: min-content;

        border-radius: 2137px;
        background-color: var(--background-color);
    }

    .pfp img {
        width: 135px;
        height: 135px;
        border-radius: 2137px;
        padding: 8px;
    }

    #username {
        margin-left: 15px;
        position: relative;
        top: calc((-135px / 2) - 15px);
        font-family: "ABC Ginto Normal";
        font-weight: 700;
        font-size: 20px;
        color: white;
        letter-spacing: -0.025em;
    }

    #username span {
        color: #b9bbbe;
    }
</style>
