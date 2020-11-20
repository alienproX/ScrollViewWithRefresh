# ScrollViewWithRefresh

SwiftUI ScrollView with Pull to Refresh.

```

func onScroll(frame: CGRect, offset: CGPoint) -> Void {
    //print("frame", frame)
    //print("offset", offset)
}
        
ScrollViewWithRefresh(refreshing: self.$model.refreshing, onScroll: onScroll) {
  LazyVStack {
      ForEach(model.data, id: \.self) { i in
          HStack {
              Text("\(i)")
              Spacer()
          }
          .background(Color(.systemGray6))
      }
      if model.shouldLoadMore {
          ProgressView()
              .onAppear {
                  model.loadMore()
              }
      } else {
          Text("No more Data")
      }

  }
}
```


![ScrollViewWithRefresh](https://raw.githubusercontent.com/cattla/cattla.github.io/master/files/ScrollViewWithRefresh.gif)
