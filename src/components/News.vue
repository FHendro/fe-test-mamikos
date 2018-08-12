<template>
    <div class="news-section">
        <div class="container">
            <div class="row">
                
                <div class="col-md-4">
                    <div class="news-wrapper">
                        <div class="news-date">06.10</div>
                        <div class="news-content">
                            <h3>Doloremque laudantium totam sequi</h3>
                            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illo saepe assumenda dolorem modi, expedita voluptatum ducimus necessitatibus. Asperiores quod reprehenderit necessitatibus harum, mollitia, odit et consequatur maxime nisi amet doloremque.</p>
                            <img src="@/assets/images/arrow.png" alt="" class="arrow">
                        </div>
                        
                    </div>
				</div>

                <div class="col-md-4">
                    <div class="news-wrapper">
                        <div class="news-date">06.10</div>
                        <div class="news-content">
                            <h3>Doloremque laudantium totam sequi</h3>
                            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illo saepe assumenda dolorem modi, expedita voluptatum ducimus necessitatibus. Asperiores quod reprehenderit necessitatibus harum, mollitia, odit et consequatur maxime nisi amet doloremque.</p>
                            <img src="@/assets/images/arrow.png" alt="" class="arrow">
                        </div>
                        
                    </div>
				</div>

                <div class="col-md-4">
                    <div class="news-wrapper">
                        <div class="news-date">06.10</div>
                        <div class="news-content">
                            <h3>Doloremque laudantium totam sequi</h3>
                            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illo saepe assumenda dolorem modi, expedita voluptatum ducimus necessitatibus. Asperiores quod reprehenderit necessitatibus harum, mollitia, odit et consequatur maxime nisi amet doloremque.</p>
                            <img src="@/assets/images/arrow.png" alt="" class="arrow">
                        </div>
                        
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

.news-section {
    background: #262A35;
    margin-top: 40px;
    padding: 60px 0;
}

.news-wrapper {
    display: flex;
    align-items: flex-start;
}

.news-date {
    color: #2D6F8E;
    font-size: 28px;
    font-weight: 500;
}

.news-content {
    margin-left: 30px;
}

.news-content h3 {
    font-size: 14px;
    cursor: pointer;
}

.arrow {
    cursor: pointer;
}

</style>
