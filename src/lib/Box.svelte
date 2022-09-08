<script>
    import { scale } from 'svelte/transition';

    export let user = {
        username: 'MExample',
        tag: 1234,
        id: '999999999999999999',
        bannerColor: '#063DF1',
        profilePictureUrl: 'https://cdn.discordapp.com/avatars/282861813215789058/5d1277d788ff2ed8f86315b39e1705b7.png?size=256',
    }

    function sendMessageBtn() {
        window.open(`https://discord.com/users/${user.id}`, '_blank');
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

        <div class="underbanner">
            <div class="pfp">
                <!-- svelte-ignore a11y-img-redundant-alt -->
                <img src={user.profilePictureUrl} alt="profile picture">
            </div>

            <div class="ub-things">
                <div class="bagdes">
                    <img src="/public/hs-brilliance.svg" alt="">
                </div>

                <div class="buttons">
                    <button on:click={sendMessageBtn}>Send Message</button>
                    <svg class="additionalActionsIcon-3Cy8UU" aria-hidden="true" role="img" width="24" height="24" viewBox="0 0 24 24"><g fill="none" fill-rule="evenodd"><path d="M24 0v24H0V0z"></path><path fill="currentColor" d="M12 16c1.1045695 0 2 .8954305 2 2s-.8954305 2-2 2-2-.8954305-2-2 .8954305-2 2-2zm0-6c1.1045695 0 2 .8954305 2 2s-.8954305 2-2 2-2-.8954305-2-2 .8954305-2 2-2zm0-6c1.1045695 0 2 .8954305 2 2s-.8954305 2-2 2-2-.8954305-2-2 .8954305-2 2-2z"></path></g></svg>
                </div>
            </div>
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
        border-radius:    8px;

        position:  absolute;
        top:       50vh;
        left:      50vw;
        transform: translate(-50%, -50%);

        width:     600px;
        height:    536px;
        z-index:   2137;
    }

    header {
        height: 240px;
        border-bottom: 1px solid #32353b;
    }

    .banner {
        width: 100%;
        height: 120px;
        background-color: var(--banner-color);
        border-top-left-radius: 8px;
        border-top-right-radius: 8px;
    }

    .pfp {
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

    .underbanner {
        position: relative;
        top: calc(-135px / 2);
        left: 15px;
        width: calc(600px - 30px);
        height: 135px;
        display: flex;
    }

    .ub-things {
        display: flex;
        align-items: center;
        justify-content: space-between;

        width: 100%;
        padding-top: calc(135px / 2);
        padding-left: 8px;
    }

    .ub-things div {
        display: flex;
        align-items: center;
    }

    .buttons button {
        font: 400 13.3333px "ABC Ginto Normal";
        color: white;
        background-color: #2D7D46;
        border: none;
        border-radius: 3px;
        margin-right: 10px;

        transition: background-color .17s ease;
    }

    .buttons button:hover {
        background-color: #215B32;
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
