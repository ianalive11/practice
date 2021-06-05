<template>
<div class="container">
    <nav class="header">
        <a class="item" href=""><div>apple</div></a>
        <a class="item" href=""><div>apple</div></a>
        <a class="item" href=""><div>apple</div></a>
        <!-- <div class="item"><a href="#">apple</a></div>
        <div class="item"><a href="#">banana</a></div>
        <div class="item"><a href="#">cat</a></div> -->
    </nav>
    <main>
        <table>
            <thead>
                <tr>
                    <th v-for="item in table" :key="item">{{item}}</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(cnontent,i) in tableContent" :key="i">
                    <td>{{cnontent.name}}</td>
                    <td>{{cnontent.amount}}</td>
                    <td>{{cnontent.price}}</td>
                </tr>
            </tbody>
        </table>
        <div class="mixin">
            <div class="left">
                <div class="vertical_absolute">絕對定位</div>
            </div>
            <div class="center">
                <div class="vertical_transform">絕對定位</div>
            </div>
            <div class="right">
                <div class="vertical_before">偽元素</div>
            </div>
        </div>
        <div class="form">

        </div>
    </main>
</div>
</template>

<script>
import '../scss/Page.scss'
export default {
    data(){
        return {
            table: ["name","amount","price"],
            tableContent: [
                {name: 'apple',amount: '2', price: '50'},
                {name: 'banana',amount: '5', price: '100'},
                {name: 'cat',amount: '1', price: '5000'},
            ]
        }
    }
}
</script>
