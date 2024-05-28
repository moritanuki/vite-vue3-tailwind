# Vue 3 + TypeScript + Vite + Tailwind

## Setup
1. Vue 3 + TypeScript + Vite を構築する
```bash
npm create vite@latest
```

2. 上記で作成したプロジェクトディレクトリに移動しておく
  （例）プロジェクト名「vite-vue3-tailwind」の場合
```bash
cd vite-vue3-tailwind
```

3. TailwindやAutoprefixerをインストールする
```bash
npm install -D tailwindcss postcss autoprefixer
```
なぜPostCSSとAutoprefixer（PostCSSのプラグイン）もインストールしているのか？の問いに対して、[公式の説明](https://tailwindcss.com/docs/installation/using-postcss)抜粋が以下。
> Tailwind CSSをPostCSSプラグインとしてインストールすることは、webpack、Rollup、Vite、Parcelなどのビルドツールと統合する最もシームレスな方法です。

4. TailwindとPostCSSのConfigファイルを作成する
```bash
npx tailwindcss init -p
```

5. Tailwind読み込み用CSSを作成する
```bash
mkdir -p ./src/assets && echo -e "@tailwind base;\n@tailwind components;\n@tailwind utilities;" | tee ./src/assets/index.css > /dev/null
```

6. main.tsで上記のCSSを読み込む
```typescript
import { createApp } from 'vue'
import App from './App.vue'
import './assets/index.css'

createApp(App).mount('#app')
```

7. tailwind.config.jsに読み込むファイルを設定する
```javascript
export default {
  content: ['./src/**/*.{html,js,vue}'],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
