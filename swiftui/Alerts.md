### Alert

`Alert(title: Text("Alert Title"), message: Text("This is my alert."), dismissButton: .default(Text("OK")))`

### Present alert based on boolean

```
struct ContentView: View {
    @State private var showingAlert = false

    var body: some View {
        Button("Show Alert") {
            showingAlert = true
        }
        .alert(isPresented: $showingAlert) {
            Alert(title: Text("Alert Title"), message: Text("This is my alert."), dismissButton: .default(Text("OK")))
        }
    }
}
```

Presenting an alert like this will automatically set showingAlert back to false when the dismiss button is tapped.

### Add actions to alerts

```
struct ContentView: View {
    @State private var showingAlert = false

    var body: some View {
        Button("Show Alert") {
            showingAlert = true
        }
        .alert(isPresented:$showingAlert) {
            Alert(
                title: Text("Are you sure you want to delete this?"),
                message: Text("There is no undo"),
                primaryButton: .destructive(Text("Delete")) {
                    print("Deleting...")
                },
                secondaryButton: .cancel()
            )
        }
    }
}
```

[Hacking with Swift](https://www.hackingwithswift.com/quick-start/swiftui/how-to-show-an-alert)  
[How to show multiple alerts in a single view](https://www.hackingwithswift.com/quick-start/swiftui/how-to-show-multiple-alerts-in-a-single-view)
