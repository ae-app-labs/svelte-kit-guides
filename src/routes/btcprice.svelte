
<script context="module">
    export async function load( {fetch} ) {
        const res = await fetch('https://api.coindesk.com/v1/bpi/currentprice.json')
        const resJson = await res.json()
        const btcPrice = {
            price: resJson.bpi.USD.rate,
            lastFetch: resJson.time.updated,
        }

        if(res.ok) {
            return {
                props: {
                    btcPrice
                }
            }
        } 

        return {
            status: res.status,
            error: new Error('Could not fetch the guides')
        }
    }
</script>

<script>
    export let btcPrice
</script>

<div class="guides">
    <h1>Price in USD: {btcPrice.price}</h1>
    <h4>{btcPrice.lastFetch}</h4>
</div>

<style>
    .guides {
        margin-top: 20px;
    }
</style>