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
Step.1 ここにステータス画面を作ります
</div>

<!-- Step.3 スタイルシートを書いたら、ここにコンフィグ画面を作ります -->
<div class="status-config">
Step.3 スタイルシートを書いたら、ここにコンフィグ画面を作ります
</div>

<!-- Step.2 ステータス画面を作ったら、ここにスタイルシートを書きます -->
Step.2 ステータス画面を作ったら、ここにスタイルシートを書きます