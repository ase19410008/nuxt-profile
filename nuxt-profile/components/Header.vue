<template>
    <header class="header">
        <h1 class="site-title">
            <a href="index.html">
                <p>名前</p>
            </a>
        </h1>
        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#images">images</a></li>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
/*-------------------------------------------
ヘッダー
-------------------------------------------*/
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0 auto;
    margin-left: 2rem;
    margin-right: 2rem;
    ul {
        display: flex;
        padding: 10px 0;
    }
    li {
        margin-left: 30px;
        a {
            color: #24292e;
            &:hover {
                opacity: 0.7;
            }
        }
    }
}
</style>