## VIPER

![image](https://user-images.githubusercontent.com/70689381/162989587-63668b64-6d12-4d8d-9758-aa29841c190a.png)

### ๐ย  View-Interactor-Presenter-Entity-Router์ ์ฝ์

### ๐ย  Router

- ์ ์ฒด ๋ชจ๋์ ๋ํ ์ง์์  (= ์ ์ฒด ํ๋ฆ์ด ๋ค์ด์ด)

- App์ ์ผ๋ถ๋ฅผ ์๊ณ  ์๋ ๋ผ๋ฆฌ์  ๋ชจ๋

- ๋ค๋ฅธ ๋ผ์ฐํฐ๋ฅผ ํธ์ถํ  ์ ์์

### ๐ย  Entity

- ์ฑ์ ๊ตฌ์ฑํ๋ ์ ๋ณด

- `Model`์ ํด๋นํ๋ ๋ถ๋ถ

### ๐ย  Presenter

- ์ ์ฐฉ์ 

- `router`, `interactor`, `view`๋ฅผ ์ฐธ์กฐ

- interactor์๊ฒ ์์์ ์ํ์ ์ง์ํจ

- ๋ทฐ๋ฅผ ์๋ฐ์ดํธํจ

### ๐ย  View

- UIView, UIViewController ๋ ๋ค ํด๋น

    - UI ์์ ๋ฟ๋ง์ด ์๋, ๊ด๋ จ ์์๋ค๋ ์ฒ๋ฆฌํ  ์ ์์

### ๐ย  Interaction

- App์ ์ฒ์ถ !

- ํต์ฌ ์ํธ์์ฉ์ ์ํ
    - ex - ์ธ์คํ๊ทธ๋จ ํผ๋ ๊ฐ์ ธ์ค๊ธฐ
    
- `entity` (๋ชจ๋ธ) ์ค์ ์ด ํ์ํจ

- `presenter`๋ก ์ ๊ทผํด ์ํธ์์ฉ์ ์ํํจ
    - ex - API ํธ์ถ

---

### ์ถ์ฒ
- [Swift: VIPER Design Pattern (Architecture, 2022, Xcode 12, Swift 5) - iOS Development](https://www.youtube.com/watch?v=hFLdbWEE3_Y)
