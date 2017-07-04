# Code Together: Let's make iPhone app in an hour

  <div style="text-align:center"><img src ="https://github.com/iosClassForBeginner/mapApp/preview.PNG" width="50%" height="50%"/></div>  

  Thank you for visiting our account. We are going to make a map app in an hour. If would you like to study yourself before hands-on, or review what you have learned in the session, please use the following material.

## Meetup
We are providing free hands-on on a monthly basis

https://www.meetup.com/iOS-Development-Meetup-for-Beginner/

## Do you need a tutor?
We also hold face-to-face or group lesson for individual interested in making iOS app themselves

http://ios-class-for-beginner.esy.es/

## Development Environment
  Xcode 8.3.2 / Swift 3

# Full procedure
## 0, Create your project

> 0-1. Open Xcode  
> 0-2. Select <sup>Create a new Xcode project</sup> or Go to <code>File</code> → <code>New</code> → <code>Project...</code>  
> 0-3. Select <sup>Single View Application</sup> and then tap <sup>Next</sup>  
> 0-4. Fill <sup>Product name</sup> and then tap <sup>Next</sup>  
> 0-5. Select the place for saving your project and then tap <sup>Create</sup>  

## 1, Design your app
#### 🗂 Main.storyboard

> 2-1. Add a <code>MKMapView</code> to your View Controller
<details>
  <summary>View Gif</summary>
  <div style="text-align:center"><img src ="https://github.com/iosClassForBeginner/speech-en/blob/master/resources/0.gif" />     </div>
</details>

> 2-2. Add a <code>UISegmentControl</code> to your View Controller
<details>
  <summary>View Gif</summary>
  <div style="text-align:center"><img src ="https://github.com/iosClassForBeginner/speech-en/blob/master/resources/0.gif" />     </div>
</details>

> 2-3. Apply autoresizing for map and segment control
<details>
  <summary>View Gif</summary>
  <div style="text-align:center"><img src ="https://github.com/iosClassForBeginner/speech-en/blob/master/resources/0.gif" />     </div>
</details>


## 2, Connect UI components to the ViewController
#### 🗂 Main.storyboard → ViewController.swift  
  ★  control + drag in storyboard to create a control segue
  
> 3-1. Connect "MKMapView"
> <details>
  <summary>View Gif</summary>
  <div style="text-align:center">
    <img src ="https://github.com/iosClassForBeginner/speech-en/blob/master/resources/3-1.gif" />
  </div>
 </details>

> 3-2. Add action of "UIButton"
> <details><summary>View Gif</summary><div style="text-align:center"><img src ="https://github.com/iosClassForBeginner/speech-en/blob/master/resources/3-2.gif" /></div></details>

## 4, Add code blocks in ViewController.swift
#### 🗂 ViewController.swift  
> ★ It's preferable to write following code yourself. It will help you to understand code more.

```Swift  
import UIKit
import AVFoundation     // Import AVFoundation to access speech fearure

class ViewController: UIViewController
{
    @IBOutlet var txtv: UITextView!
    var synthesizer = AVSpeechSynthesizer()

    override func viewDidLoad() {
        super.viewDidLoad()
    }

    @IBAction func tappedSpeech(_ sender: Any)
    {
        // Create contents
        let contents = AVSpeechUtterance(string: txtv.text ?? "")

        // Set language
        contents.voice = AVSpeechSynthesisVoice(language: "en-US")

        // Speak
        synthesizer.speak(contents)
    }
}
```
