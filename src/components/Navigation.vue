<template>
<nav class="navbar navbar-default">
    <div class="container">
      <!-- Brand and toggle get grouped for better mobile display -->
      <div class="navbar-header">
        
        <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1"
          aria-expanded="false">
          <span class="sr-only">Toggle navigation</span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>

        <a class="navbar-brand" href="#">
          <div class="logo">
            <img src="@/assets/images/logo.png" alt="">
            <div class="title">
              <span class="title-company-name">Company name</span>
              <br>
              <span class="title-company-tagline">tagline goes here</span>
            </div>
          </div>
        </a>

      </div>

      <!-- Collect the nav links, forms, and other content for toggling -->
      <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
        <ul class="nav navbar-nav navbar-right">
          <li class="active">
            <a href="#">Home</a>
          </li>
          <li>
            <a href="#">News</a>
          </li>
          <li>
            <a href="#">Live cameras</a>
          </li>
          <li>
            <a href="#">Photos</a>
          </li>
          <li>
            <a href="#">Contact</a>
          </li>
        </ul>
      </div>
      <!-- /.navbar-collapse -->
    </div>
    <!-- /.container-fluid -->
  </nav>
  </template>
<script>
export default {

}
</script>

<style scoped>

.navbar-default {
    background: #1E212A;
    padding: 50px 25px;
    margin: 0;
    border: 0;
    box-shadow: none;
    border-radius: 0;
}

.navbar.navbar-default .navbar-collapse {
    border: none;
    box-shadow: none;
}

.navbar-default .navbar-brand {
    color: #fff;
}

.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
    color: #228FB9;
}


.navbar-default .navbar-nav>li>a {
    color: #fff;
    margin-left: 10px;
    padding: 5px 30px;
    border: 2px solid transparent;
    border-radius: 50px;
}

.navbar-default .navbar-nav>li>a:hover,
.navbar-default .navbar-nav>li>a:focus {
    color: #228FB9;
    border: 2px solid #228FB9;
}

.navbar-default .navbar-nav>.active>a,
.navbar-default .navbar-nav>.active>a:hover,
.navbar-default .navbar-nav>.active>a:focus {
    color: #228FB9;
    border: 2px solid #228FB9;
    background: #1E212A;
}

.navbar-default .navbar-toggle {
    border: 2px solid transparent;
    border-radius: 100px;
    padding: 20px 15px;
}

.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
    background-color: #1E212A;
    border: 2px solid #228FB9;
}

.navbar-default .navbar-toggle .icon-bar {
    background-color: #CCC;
}

.navbar-brand .logo {
    display: flex;
}

.navbar-brand .title {
    margin-left: 12px;
}

.title-company-name{
    font-weight: 500;
}

.title-company-tagline {
    color: #787B84;
    font-weight: 300;
    font-size: 12px;
}

@media (max-width: 1000px) {

/* OVERRIDE DEFAULT NAVBAR BREAKPOINT
---------------------------------------------------------------
 */

    .navbar-header {
        float: none;
    }
    .navbar-left,.navbar-right {
        float: none !important;
    }
    .navbar-toggle {
        display: block;
    }
    .navbar-collapse {
        border-top: 1px solid transparent;
        box-shadow: inset 0 1px 0 rgba(255,255,255,0.1);
    }
    .navbar-fixed-top {
        top: 0;
        border-width: 0 0 1px;
    }
    .navbar-collapse.collapse {
        display: none!important;
    }
    .navbar-nav {
        float: none!important;
        margin-top: 7.5px;
    }
    .navbar-nav>li {
        float: none;
    }
    .navbar-nav>li>a {
        padding-top: 10px;
        padding-bottom: 10px;
    }
    .collapse.in{
        display:block !important;
    }

/* MOBILE NAV STYLING
----------------------------------------------------------
*/

    .navbar-default .navbar-nav>li>a {
        text-align: center;
        border-radius: 0;
        margin-left: 0;
        padding: 20px 0;
    }
    .navbar-default .navbar-nav>li:not(:last-child)>a {
        border-bottom: 0.5px solid #383C48;
    }
    .navbar-default .navbar-nav>.active>a,
    .navbar-default .navbar-nav>.active>a:hover,
    .navbar-default .navbar-nav>.active>a:focus {
        color: #228FB9;
        border: none;
        border-radius: 0;
        border-bottom: 0.5px solid #383C48;
        background: transparent;
        box-shadow: none;
    }
    .navbar-default .navbar-nav>li>a:hover,
    .navbar-default .navbar-nav>li>a:focus {
        color: #228FB9;
        border: none;
    }
    .navbar-default .navbar-nav>li:not(:last-child)>a:hover,
    .navbar-default .navbar-nav>li:not(:last-child)>a:focus {
        border-bottom: 0.5px solid #383C48;
    }
    .navbar-nav {
        margin-top: 20px;
        background: #262A36;
        border-radius: 15px;
    }
}

@media (max-width: 320px) {
    .navbar-brand .title-company-name {
        font-size: 12px;
    }

    .navbar-brand .title-company-tagline{
        font-size: 8px;
    }
}

</style>
