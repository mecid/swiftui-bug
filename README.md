# swiftui-bug FB7133446
## Sample project for reproducing SwiftUI bug when child view's ObservableObject lose the data

### The problem:
There is a bug when a child view lose the data fetched by ObservableObject after the parent view's update/recreation process.
### Steps to reproduce

1. Open the app
2. Click on any item in the list, on details screen you can see the name of selected repo and list of repos with similar name fetched with additional request
3. Hide app
4. Open app, in the background we run ReposStore update with same query by using SceneDelegate
5. Toggle the switch
6. Toggle again

Now you can see that the list is not appearing and ReposStore object is empty.

#### NOTE: This problem appear in case when parent view updated with same Identifiable data. The bug is not appearing when parents view updated with different data.

