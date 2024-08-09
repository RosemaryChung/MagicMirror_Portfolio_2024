# MagicMirror
A "MagicMirror" is a reflective screen that functions as a mirror and shows electronic graphics.  The screen elements are fully customizable and can be used for anything you want. I have made my screen into a mindful-learning mirror. 

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Rosemary C | Roedean School| Astrophysics | Junior


![Headstone Image](headstone pic.HEIC)

# First Milestone
<iframe width="560" height="315" src="https://www.youtube.com/embed/Yf0cqYxd6_s?si=ah7rs5jTVFwmRHP3" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

I started this project during another summer program abroad. This resulted in huge issues when connecting my devices to the same secure network because I had to register the Raspberry Pi as a non-standard device (essentially I couldn't navigate my Raspberry Pi remotely on my MacBook). I could only connect both devices to a public network- which was a problem since devices were not made discoverable by default (I assume for privacy reasons as it is a public network). I was using the wireless keyboard and the touchscreen to navigate everything (sadly my mouse was dysfunctional).

When I finally returned home, all connections went well so I could finally start remotely editing, removing, and adding modules to my MagicMirror Interface. 

The first module I tried to add was called MMM-JustForTodayMeditation but it was persistently giving me problems so I resorted to finding other modules to add on the assumption that the code for the JustForTodayMeditation was faulty, outdated, or wrong in some way. Following this, I added the MMM-LearnLanguage module and the MMM-BreathWork module. I doubled the LearnLanguage module just so I could have the dynamic of learning two words from different languages per day.



# Final Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/_hrrW1tbz0o?si=uJ8Ln9z1r9JdYbKd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

For the last milestone, I was mostly adding and customizing modules and figuring out how I wanted to display the mirror. 

I had two options for displaying the mirror: either using the 7" display sent by BlueStamp and adding a frame around it, or using a bigger monitor that isn't being used by anyone in my home. Initially, I wanted to use the bigger monitor because I thought it would embody more of a mirror than the small one would allow for. When I was applying the reflective film to the bigger screen, I couldn't apply it smoothly without bumps and bubbles. Because of this I just ended up applying the film on the smaller display instead. In the end, I quite prefer the smaller display since I now plan to use this mirror on my bedside table.

When I was adding new modules, I had issues with modules that had "var config". Every time I added them to my code, the display would not load, and as soon as I removed them everything started to work again. I was pretty bummed about that because I wanted to include a dad jokes module which I found super funny. On the topic of modules, when I was making the motion detection code for my proposed gesture-controlled Spotify module, I didn't realise the difference between the code for a motion sensor and for a USB webcam. Because of this, I ended up just scrapping the whole Spotify module and using a pre-existing motion detection module that uses the USB webcam to turn the screen display on/off.


# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

# Bill of Materials


| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Raspberry Pi Kit | Portable computer that controls electronic components | $98 | <a href="https://www.amazon.com/RasTech-Raspberry-Starter-Heatsink-Screwdriver/dp/B0C8LV6VNZ/ref=sr_1_4?crid=3506HY00MCGVM&dib=eyJ2IjoiMSJ9._zkM62vSQ8p7tNr88715LdMv_qHh72Je-tkF9PXEa3chDE53QT4aZu4AGAb4ihE61QY4ZD55nKF6Fp2Kfs8t7AbafM_JrlJFfHo9OB4eAVGqa0EB-7aoBQHPmhKHZ2MW8ny-Kd44bMVlVxPlTWVk5YHIN5P3uKVqrE5Dcal0rKkHny-O6Xyb5ux2AOU6OwVbkag_bqBX66RQNRrgBuz-0pS43mcx93IZTQA9R8NaJJypYU2HAycp-XicTFmyU60a01Nfm9iuyo6B9yA8ppN3OQQyJ-NQ9xyNPxfTLwkqtng.yAYpU6outhQcZmOZhN9Wb6yTw7A85CNUbXZguGInZNg&dib_tag=se&keywords=raspberry%2Bpi%2Bkit&qid=1718848547&s=electronics&sprefix=rasbperry%2Bpi%2Bkit%2Celectronics%2C83&sr=1-4&th=1"> Link </a> |
|7-inch LCD Display | Used to show the Raspberrypi interface | $46 | <a href="https://www.amazon.com/Hosyond-Display-1024%C3%97600-Capacitive-Raspberry/dp/B09XKC53NH/ref=sr_1_3?crid=1KKB9WC62OIAD&keywords=raspberry%2Bpi%2Bips&qid=1685911698&s=electronics&sprefix=raspberry%2Bpi%2Bips%2B%2Celectronics%2C87&sr=1-3&th=1"> Link </a> |
| Mouse & Keyboard | Display navigation | $20 | <a href="https://www.amazon.com/gp/product/B07XDWCLYF/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1"> Link </a> |
| USB-C to USC adaptor| Needed to flash the SD card | $35 | <a href="https://en.j5create.com/products/jch342e?variant=43997310386425"> Link </a> |


