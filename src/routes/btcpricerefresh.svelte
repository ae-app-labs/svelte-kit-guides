<script>
    let btcPrice = {
        price: 0,
        lastFetch: ""
    }

    const fecthPrice = async () => {
        const res = await fetch('https://api.coindesk.com/v1/bpi/currentprice.json')
        const resJson = await res.json()
        const btcPrice = {
            price: resJson.bpi.USD.rate,
            lastFetch: resJson.time.updated,
        }

        if(res.ok) {
            return {
                btcPrice
            }
        } 
    }

    // window object is not defined on the server
    //window.setTimeout( fecthPrice, 3000);
</script>

<div class="container">
    <h1>Price in USD: {btcPrice.price}</h1>
    <h4>{btcPrice.lastFetch}</h4>
</div>

<style>
    .container {
        margin-top: 20px;
    }
</style>