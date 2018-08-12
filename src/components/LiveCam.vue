<template>
    <div class="live-cam-section">
        <div class="container">
            <h1 class="live-cam-title">Live cameras</h1>

            <div class="row">

                <div class="col-md-3 col-sm-6">
                    <div class="live-cam-wrapper">
                        <div class="img-wrapper">
                            <img src="@/assets/images/img_newyork.jpeg" class="img-responsive">
                            <img src="@/assets/images/ic_play.svg" class="icon-play">
                        </div>
                        <h3 class="city-name">New York</h3>
                        <span class="city-date">8 Oct, 8:00AM</span>
                    </div>
                </div>

                <div class="col-md-3 col-sm-6">
                    <div class="live-cam-wrapper">
                        <div class="img-wrapper">
                            <img src="@/assets/images/img_losangeles.jpeg" class="img-responsive">
                            <img src="@/assets/images/ic_play.svg" class="icon-play">
                        </div>
                        <h3 class="city-name">Los Angeles</h3>
                        <span class="city-date">8 Oct, 8:00AM</span>
                    </div>
                </div>

                <div class="col-md-3 col-sm-6">
                    <div class="live-cam-wrapper">
                        <div class="img-wrapper">
                            <img src="@/assets/images/img_chicago.jpeg" class="img-responsive">
                            <img src="@/assets/images/ic_play.svg" class="icon-play">
                        </div>
                        
                        <h3 class="city-name">Chicago</h3>
                        <span class="city-date">8 Oct, 8:00AM</span>

                    </div>
                </div>

                <div class="col-md-3 col-sm-6">
                    <div class="live-cam-wrapper">
                        <div class="img-wrapper">
                            <img src="@/assets/images/img_london.jpeg" class="img-responsive">
                            <img src="@/assets/images/ic_play.svg" class="icon-play">
                        </div>
                        <h3 class="city-name">London</h3>
                        <span class="city-date">8 Oct, 8:00AM</span>
                    </div>
                </div>

            </div>

        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>

.live-cam-section {
    margin-top: 40px;
    margin-bottom: 80px;
}

h1 {
    font-weight: 300;
    color: white;
}

img {
    border-radius: 5px;
}

.city-name {
    color : #C4C6CB;
    font-size: 18px;
    font-weight: 300;
    margin-top: 20px;
    margin-bottom: 10px;
}

.city-date {
    color : #C4C6CB;
    font-size: 12px;
    font-weight: 300;
}

.img-wrapper {
    position: relative;
}

img.icon-play { 
    position: absolute;
    width: 50px;
    height: 50px;
    top : 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    cursor: pointer;
}



</style>
