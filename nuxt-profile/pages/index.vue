<template>
  <div>
    <Header/>
    <!-- メインの情報 -->
    <main>
        <div class="container">
            <img src="https://www.pakutaso.com/shared/img/thumb/redsg13302_TP_V.jpg" alt="トプ画"/>
        </div>

        <About/>

        <Images/>
    </main>

    <!-- フッター -->
    <Footer/>
  </div>
</template>

<style lang="scss" scoped>
@charset "UTF-8";

/*-------------------------------------------
デフォルトのスタイルを設定（基本いじらない）
-------------------------------------------*/
html {
    font-size: 100%;
}
body {
    color: #383e45;
    font-size: 0.9rem;
}
a {
    text-decoration: none;
}
img {
    max-width: 100%;
}
li {
    list-style: none;
}

/*-------------------------------------------
コンテンツ事のスタイル変数
-------------------------------------------*/
$content-max-width: 960px;
$max_sp: 600px;

/*-------------------------------------------
共通のスタイル
-------------------------------------------*/

/* コンテンツの範囲を共通で持つ */
@mixin contents($max-width: $content-max-width) {
    max-width: $max-width;
    margin: 0 auto 100px auto;
    padding: 0 4%;
    text-align: center;
}

/* モバイル版のメディアクエリを持つ */
@mixin max_sp {
    @media screen and (max-width: $max_sp) {
        @content;
    }
}



/*-------------------------------------------
複数使うスタイル
-------------------------------------------*/
.site-title {
    line-height: 1px;
    padding: 10px 0;
    a {
        display: block;
    }
}

/*-------------------------------------------
body内の全体のスタイル
-------------------------------------------*/
.container {
    margin-bottom: 80px;
    img {
        width: 100%;
        height: 600px;
        object-fit: cover;
    }
    /*-------------------------------------------
    About
    -------------------------------------------*/
    &__about {
        @include contents;
        &__content {
            display: flex;
            justify-content: center;
            align-items: center;
        }
        img {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            margin-right: 30px;
        }
        &--text {
            text-align: left;
        }
    }
    /*-------------------------------------------
    images
    -------------------------------------------*/
    &__images {
        @include contents;
        ul {
            display: flex;
            justify-content: space-between;
        }
        li {
            width: 32%;
        }
    }
}

/*-------------------------------------------
モバイル版の見た目にする
-------------------------------------------*/
@include max_sp {
    .container {
        img {
            // height: calc(100vh - 60px);
            height: 100vh;
        }
        &__about {
            &__content {
                flex-direction: column;
            }
            img {
                margin-right: 0;
            }
        }
        &__images {
            ul {
                flex-direction: column;
            }
            li {
                width: 100%;
                margin-bottom: 30px;
            }
        }
    }
}
</style>