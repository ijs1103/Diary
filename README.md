# Diary
![Simulator Screen Recording - iPod touch (7th generation) - 2023-01-21 at 23 39 24](https://user-images.githubusercontent.com/42196410/213871830-9d72be2f-eae9-48f2-a1de-93c2f1ba3814.gif)

## 🧩 개요

- 일기 생성/수정/삭제/즐겨찾기 기능 
- userDefaults에 data를 저장
- NotificationCenter를 통한 상태관리(data 변화를 감지하며 구독) 

## 🤔 배운 내용

### ✔️ NotificationCenter를 통한 상태관리

데이터의 변경을 발생시키는 `viewController`에서는 `NotificationCenter.default.post`

데이터의 변경을 구독하는 `viewController`에서는 `NotificationCenter.default.addObserver`를 사용.

데이터의 변경을 구독시 메모리에서의 해제를 위해, 반드시 소멸자에 구독을 해제하는 `NotificationCenter.default.removeObserver(self)` 코드 추가 

## ✔️ collectionView data insert/delete

컬렉션뷰에서 데이터를 추가/삭제 할때의 순서는 다음과 같다. 

1) 데이터가 저장된 배열에서 해당 데이터를 추가 / 삭제

2) `insertItems / deleteItems` 메서드 호출

기본적으로, `insertItems / deleteItems` 메서드에는 `reloadData` 메서드가 포함되어 있기 떄문에

`insertItems / deleteItems`메서드 호출시에는 `reloadData` 메서드를 호출할 필요가 없다.

그러므로, 데이터를 수정할 때에는 reloadData 메서드를 호출해야한다. 
