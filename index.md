# MagicMirror
A "MagicMirror" is a reflective screen that functions as a mirror and shows electronic graphics.  The screen elements are fully customizable and can be used for anything you want. I have made my screen into a mindful-learning mirror. 

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Rosemary C | Roedean School| Astrophysics | Junior


![Headstone Image](/MagicMirror_Portfolio_2024/headstone pic.png)

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


```c++

let config = {
	address: "localhost",	// Address to listen on, can be:
							// - "localhost", "127.0.0.1", "::1" to listen on loopback interface
							// - another specific IPv4/6 to listen on a specific interface
							// - "0.0.0.0", "::" to listen on any interface
							// Default, when address config is left out or empty, is "localhost"
	port: 8080,
	basePath: "/",	// The URL path where MagicMirror² is hosted. If you are using a Reverse proxy
									// you must set the sub path here. basePath must end with a /
	ipWhitelist: ["127.0.0.1", "::ffff:127.0.0.1", "::1"],	// Set [] to allow all IP addresses
									// or add a specific IPv4 of 192.168.1.5 :
									// ["127.0.0.1", "::ffff:127.0.0.1", "::1", "::ffff:192.168.1.5"],
									// or IPv4 range of 192.168.3.0 --> 192.168.3.15 use CIDR format :
									// ["127.0.0.1", "::ffff:127.0.0.1", "::1", "::ffff:192.168.3.0/28"],

	useHttps: false,			// Support HTTPS or not, default "false" will use HTTP
	httpsPrivateKey: "",	// HTTPS private key path, only require when useHttps is true
	httpsCertificate: "",	// HTTPS Certificate path, only require when useHttps is true

	language: "en",
	locale: "en-US",
	logLevel: ["INFO", "LOG", "WARN", "ERROR"], // Add "DEBUG" for even more logging
	timeFormat: 24,
	units: "metric",

	modules: [
		{
			module: "alert",
		},
		{
			module: "updatenotification",
			position: "top_bar"
		},
		{
			module: "clock",
			position: "top_left"
		},
		{
			module: "compliments",
			position: "top_left"
		},
		{
			module: "weather",
			position: "top_right",
			config: {
				weatherProvider: "openmeteo",
				type: "current",
				lat: -25.975300,
				lon: 28.118870
			}
		},
		{
			module: "weather",
			position: "top_right",
			header: "Weather Forecast",
			config: {
				weatherProvider: "openmeteo",
				type: "forecast",
				lat: -25.975300,
				lon: 28.118870
			}
		},
		{
			module: "MMM-Breathwork",
			position: "bottom_right",
			size: "400px"
		},
		{
			module: "MMM-learnlanguage",
			position: "top_left",
			config: {
			  language: "italian",
			  nextWordInterval: 24*60*60*1000,
			  showpair: "showboth",
			  toggleInterval: 5*1000,
			  wordpaircssclassname: "bright medium"
			}
		  },
		  {
			module: "MMM-learnlanguage",
			position: "top_left",
			config: {
			  language: "japanese",
			  nextWordInterval: 24*60*1000,
			  showpair: "showboth",
			  toggleInterval: 5*1000,
			  wordpaircssclassname: "bright medium"
			}
		  },
		  {
			module: 'MMM-Planetarium',
			position: 'fullscreen_below', //Recommended
			config: {
			  latitude:  -25.975300, //Your position
			  longitude: 28.118870,
			  az: 0, // Azimuth : 0 means North, 90 means East, 180 means South, ...
			  panoffset: -0.1, // panning step by AZ
			  paninterval: 200, // milliseconds. 0 => no pan.
			  opacity: "70%",
			}
		  },
		  {
			module: 'MMM-Motion-Detection',
			config: {
				// force the use of a usb webcam on raspberry pi
				useUSBCam: true,
				// recognition interval in seconds (smaller number = faster but more CPU intensive!)
				interval: 1,
				// Notificaiton Delay after movement stops being sensed (in seconds).
				motionStopDelay: 120,
				// Threshold for motion detection, smaller numbers means more sensitive
				detectionThreshold: 1000,
				// Turn off display when no motion is detected.
				turnOffDisplay: true
			}
		},
		
	]
	
};

/*************** DO NOT EDIT THE LINE BELOW ***************/
if (typeof module !== "undefined") { module.exports = config; }
'''

# Bill of Materials


| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Raspberry Pi Kit | Portable computer that controls electronic components | $98 | <a href="https://www.amazon.com/RasTech-Raspberry-Starter-Heatsink-Screwdriver/dp/B0C8LV6VNZ/ref=sr_1_4?crid=3506HY00MCGVM&dib=eyJ2IjoiMSJ9._zkM62vSQ8p7tNr88715LdMv_qHh72Je-tkF9PXEa3chDE53QT4aZu4AGAb4ihE61QY4ZD55nKF6Fp2Kfs8t7AbafM_JrlJFfHo9OB4eAVGqa0EB-7aoBQHPmhKHZ2MW8ny-Kd44bMVlVxPlTWVk5YHIN5P3uKVqrE5Dcal0rKkHny-O6Xyb5ux2AOU6OwVbkag_bqBX66RQNRrgBuz-0pS43mcx93IZTQA9R8NaJJypYU2HAycp-XicTFmyU60a01Nfm9iuyo6B9yA8ppN3OQQyJ-NQ9xyNPxfTLwkqtng.yAYpU6outhQcZmOZhN9Wb6yTw7A85CNUbXZguGInZNg&dib_tag=se&keywords=raspberry%2Bpi%2Bkit&qid=1718848547&s=electronics&sprefix=rasbperry%2Bpi%2Bkit%2Celectronics%2C83&sr=1-4&th=1"> Link </a> |
|7-inch LCD Display | Used to show the Raspberrypi interface | $46 | <a href="https://www.amazon.com/Hosyond-Display-1024%C3%97600-Capacitive-Raspberry/dp/B09XKC53NH/ref=sr_1_3?crid=1KKB9WC62OIAD&keywords=raspberry%2Bpi%2Bips&qid=1685911698&s=electronics&sprefix=raspberry%2Bpi%2Bips%2B%2Celectronics%2C87&sr=1-3&th=1"> Link </a> |
| Mouse & Keyboard | Display navigation | $20 | <a href="https://www.amazon.com/gp/product/B07XDWCLYF/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1"> Link </a> |
| USB-C to USC adaptor| Needed to flash the SD card | $35 | <a href="https://en.j5create.com/products/jch342e?variant=43997310386425"> Link </a> |
| Reflective film| Needed to make the screen a "mirror" | $20 | <a href="https://www.takealot.com/klingshield-grey-20-mirror-reflective-window-film-75cm-x-200cm/PLID73886717"> Link </a> |
| USB webcam| Needed for motion detection | $50 | <a href="https://www.takealot.com/logitech-webcam-brio-100-full-hd-webcam/PLID94054259?gclsrc=aw.ds&gad_source=1&gclid=CjwKCAjw_Na1BhAlEiwAM-dm7O7Q4Pthh4HlmkGSzVuTUwffIgyD-3AbKektb69C6bnrGAyil2oOhRoC5XcQAvD_BwE&gclsrc=aw.ds"> Link </a> |


