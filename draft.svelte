<script>
	//ここにはJavaScriptが書かれています

	import { beforeUpdate } from "svelte";

	//変数を初期化しています。
	let name = "name";
	let lv = 10;
	let max_hp = 1000;
	let hp = 80;
	let max_mp = 10;
	let mp = 8;
	let agi = 5;
	let tec = 2;
	let str = 9;
	let luc = 1;
	let text = `I'm stronger.`;

	//なにか変化がある毎に、ここで値を計算しています。
	beforeUpdate(() => {
	  max_hp = lv * str;
	  max_mp = Math.round((lv * agi) / 2);
	});
</script>

<!-- Step.1 ここにステータス画面を作ります -->
<div class="status-view">
	<div class="status-image">
		{name}<br>
		<img src="/alienYellow.png" alt="character" />
	</div>
	<div class="status-data">
		Lv: {lv}<br>
		HP: {hp}/ {max_hp}<br>
		MP: {mp}/ {max_mp}<br>
		<br>
		AGI: {agi}  STR: {str}<br>
		TEC: {tec}  LUC: {luc}
	</div>
	<div class="status-text">
		{text}
	</div>
</div>

<!-- Step.3 スタイルシートを書いたら、ここにコンフィグ画面を作ります -->
<div class="status-config">
	config<br>
	name : <input type="text" maxlength="16" bind:value="{name}" />
	<br>
	Lv : <input type="number" min="1" max="99" bind:value="{lv}" />
	<br>
	hp: <input type="number" min="0" max="{max_hp}" bind:value={hp} />
	mp: <input type="number" min="0" max="{max_mp}" bind:value={mp} />
	<br>
	AGI: <input type="number" min="1" max="99" bind:value={agi} />
	STR: <input type="number" min="1" max="99" bind:value={str} />
	<br>
	TEC: <input type="number" min="1" max="99" bind:value={tec} />
	LUC: <input type="number" min="1" max="99" bind:value={luc} />
	<br>
	text : <br>
	<textarea bind:value="{text}"></textarea>
</div>

<!-- Step.2 ステータス画面を作ったら、ここにスタイルシートを書きます -->
<style>
	.status-view {
	  width: 320px;
	  height: 240px;
	  margin: 2em auto;
	  padding: 1em;
	  background-color: blue;
	  color: white;
	  display: flex;
	  flex-wrap: wrap;
	  text-shadow: 1px 1px black;
	  font-family: monospace;
	  font-size: 16px;
	}
	.status-image {
	  width: 128px;
	}
	.status-data {
	  flex-grow: 1;
	  padding-left: 1em;
	}
	.status-text {
	  width: 100%;
	  padding: 0.5em;
	  border: 2px ridge white;
	  overflow: hidden;
	}
	img {
	  display: block;
	  margin: auto;
	}
	.status-config {
	  width: 320px;
	  margin: 1em auto 2em;
	  padding: 1em;
	  border: 1px solid black;
	  line-height: 2em;
	}
</style>