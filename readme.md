# SoundCloudRequestBuilder

## Install
- Drag and drop xcframework file to your project. 
- Select `Embed & Sign` in `Frameworks, Libraries and Embedded Content` section
## Usage
Class SCRequestBuilder is used for create URLRequest object that fetch data from SoundCloud. 
```swift
let urlRequest = SCRequestBuilder.request(for: .chart(chartID: "soundcloud:genres:all-music"))

let task = URLSession.shared.dataTask(with: request) { data, response, error in
    guard let data = data,
            let json = try? JSONSerialization.jsonObject(with: data)
    else { return }
    
    print(json)
}

task.resume()
```