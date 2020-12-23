## Observable

### 1. Observable과 Observer

- ReactiveX에서 옵저버는 Observable을 구독
- Obseravable이 배출하는 하나 또는 연속된 항목에 옵저버는 반응
- 이러한 패턴은 동시성 연산을 가능하게 함 -->  Observable이 객체를 배출할 때까지 기다릴 필요 없이 어떤 객체가 배출되면 그 시점을 감시하는 관찰자를 옵저버 안에 두고 그 관찰자를 통해 배출 알림을 받으면 되기 때문

Observable과 옵저버가 무엇인지(그리고 어떻게 옵저버가 observable을 구독하는지) 

다양한 Observable 연산자를 어떻게 Obseravable에 연결 시키는지 

어떻게 Observable의 행동을 변경 시킬 수 있는지 설명할 것이다.

observable == observable sequence == sequence



#### Observable 생명주기(Lifecycle)

- Observable은  3가지 event를 전달

  - **Next (Emission)** : Next 이벤트를 통해 element를 방출

  <img src = "image/01/03.png" width = "530">

  - **Error (Notification)** : 에러로 인한 이벤트 종료 - 라이프사이클에서 가장 마지막에 전달

  <img src = "image/01/02.png" width = "600">

  - **Completed(Notification)** : 이벤트 방출을 완료하고 정상 종료

  <img src = "image/01/01.png" width = "600">

```swift
/// **next\* (error | completed)**
public enum Event<Element> {
    /// Next element is produced.
    case next(Element)

    /// Sequence terminated with an error.
    case error(Swift.Error)

    /// Sequence completed successfully.
    case completed
}
```







