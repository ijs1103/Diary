# Diary
![Simulator Screen Recording - iPod touch (7th generation) - 2023-01-21 at 23 39 24](https://user-images.githubusercontent.com/42196410/213871830-9d72be2f-eae9-48f2-a1de-93c2f1ba3814.gif)

## ๐งฉ ๊ฐ์

- ์ผ๊ธฐ ์์ฑ/์์ /์ญ์ /์ฆ๊ฒจ์ฐพ๊ธฐ ๊ธฐ๋ฅ 
- userDefaults์ data๋ฅผ ์ ์ฅ
- NotificationCenter๋ฅผ ํตํ ์ํ๊ด๋ฆฌ(data ๋ณํ๋ฅผ ๊ฐ์งํ๋ฉฐ ๊ตฌ๋) 

## ๐ค ๋ฐฐ์ด ๋ด์ฉ

### โ๏ธ NotificationCenter๋ฅผ ํตํ ์ํ๊ด๋ฆฌ

๋ฐ์ดํฐ์ ๋ณ๊ฒฝ์ ๋ฐ์์ํค๋ `viewController`์์๋ `NotificationCenter.default.post`

๋ฐ์ดํฐ์ ๋ณ๊ฒฝ์ ๊ตฌ๋ํ๋ `viewController`์์๋ `NotificationCenter.default.addObserver`๋ฅผ ์ฌ์ฉ.

๋ฐ์ดํฐ์ ๋ณ๊ฒฝ์ ๊ตฌ๋์ ๋ฉ๋ชจ๋ฆฌ์์์ ํด์ ๋ฅผ ์ํด, ๋ฐ๋์ ์๋ฉธ์์ ๊ตฌ๋์ ํด์ ํ๋ `NotificationCenter.default.removeObserver(self)` ์ฝ๋ ์ถ๊ฐ 

## โ๏ธ collectionView data insert/delete

์ปฌ๋ ์๋ทฐ์์ ๋ฐ์ดํฐ๋ฅผ ์ถ๊ฐ/์ญ์  ํ ๋์ ์์๋ ๋ค์๊ณผ ๊ฐ๋ค. 

1) ๋ฐ์ดํฐ๊ฐ ์ ์ฅ๋ ๋ฐฐ์ด์์ ํด๋น ๋ฐ์ดํฐ๋ฅผ ์ถ๊ฐ / ์ญ์ 

2) `insertItems / deleteItems` ๋ฉ์๋ ํธ์ถ

๊ธฐ๋ณธ์ ์ผ๋ก, `insertItems / deleteItems` ๋ฉ์๋์๋ `reloadData` ๋ฉ์๋๊ฐ ํฌํจ๋์ด ์๊ธฐ ๋๋ฌธ์

`insertItems / deleteItems`๋ฉ์๋ ํธ์ถ์์๋ `reloadData` ๋ฉ์๋๋ฅผ ํธ์ถํ  ํ์๊ฐ ์๋ค.

๊ทธ๋ฌ๋ฏ๋ก, ๋ฐ์ดํฐ๋ฅผ ์์ ํ  ๋์๋ reloadData ๋ฉ์๋๋ฅผ ํธ์ถํด์ผํ๋ค. 
