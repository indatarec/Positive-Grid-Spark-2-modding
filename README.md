# Positive-Grid-Spark-2-modding
Article about Positive Grid Spark 2 modding 

Spark 2 is improved by a lot comparing to Spark 40 (line out, better speakers, added looper). There are two revision of Spark 2 motherboards: 
"Spark40_GEN2_Main_1.5 2024-06-07 ECB01787" mainboard 
"Spark40_GEN2_Main_2.1 2024-11-02 ECB02117" mainboard - top one on picture below.
<img width="2048" height="1152" alt="two_spark2_mobos" src="https://github.com/user-attachments/assets/59ac60f5-35a4-40da-abaa-bcd529fa382b" />
<img height="600" alt="spkmobo1a" src="https://github.com/user-attachments/assets/69ea26a8-1f72-44b9-a06a-3cf4203a8211" />
<img height="600" alt="spkmobo2a" src="https://github.com/user-attachments/assets/3176d4f5-ca7d-4797-af78-e275d2dc22a2" />

Seems they organised elements a bit and they did not downgraded as much as on second revision of Spark 40 motherboards.  

To understand what can be modded and how can be improved we need to understand some of its design decisions:


# Design considerations of Spark 2


## Spark 2 cannot be powered by power bank
I see on internet posts like this:
https://www.reddit.com/r/PositiveGridSpark/comments/1fgw2qw/higher_capacity_usb_battery_works_with_spark2/

None of Spark models can negotiate input power voltage. It does not have a electronics capable of doing such thing. While you are using Power Bank there is always negotiation phase and during usage voltage drops.
SPARK 2 / 40 cannot be powered by any power bank regardless what specification of power bank says. Spark official battery is a safe way of powering amp and you do not need to worry about using it.

Pictures below are from two dead Spark 2 models where users used power bank idea. They both are fine now, I fixed them.
<img width="960" height="540" alt="burn2" src="https://github.com/user-attachments/assets/b5cfa247-c5d2-48e6-a6d8-baaf06257233" />
<img width="960" height="540" alt="burn1" src="https://github.com/user-attachments/assets/c205614b-53d5-4b5b-b205-ef0f77ccde84" />


## MCU overheating
The only element that need to be heatsinked in Spark 2 is MCU, which is boiling hot. Unfortunately you cannot do it without voiding your warranty.
MCU is cooled with thin piece of aluminium and slice of cheese of unknown brand. It does not transfer heat effectively. This STM32H750IBK6 chip cooling is the weakest point in a rather well made amp.
<img height="600" alt="mcu" src="https://github.com/user-attachments/assets/f7479f04-f490-4f12-8480-9f3cd66bd853" />
<img height="600" alt="mcu2" src="https://github.com/user-attachments/assets/a433cd1b-b831-4064-9fa0-1f71c6f08ebd" />


## Digital audio amp
Spark 40 with first motherboard and modded in my opinion is the best sound amp Positive Grid made yet. It has good analogue amp TPA3116, which you can drive further or even replace with 70W TPA3156. Spark 2 on the other hand uses digital ACM8625P, which is already maxed out at its specs and you cannot squeeze more out of this.
<img width="746" height="780" alt="amps compare" src="https://github.com/user-attachments/assets/39395fd0-337c-427b-954a-6c108b0d9712" />

Spark 40 was designed to be 2x50W amp and driven to be 2x20W at the end. Spark 2 has 51W to be used at absolute max when you use guitar input only.
Don't get me wrong... Spark 2 is a evolution and a good one. It has much more features and does not compromise build quality.
Spark 2 is like fast and fancy hybrid car. Spark 40 is like old family car ... with V8 engine inside.


## Do not do perform Spark 2 firmware update via WiFi or via phone
Spark 2 has overcomplicated ESP32 and MCU flashing procesure. If you upgrade firmware via phone it is almost 50/50 that you will brick your device.
That's the easiest way to brick your Spark 2. Please only update via USB cable. Connection via phone app is not stable ebough and even app beeign closed in backgroud will cause Spark 2 to brick. It can be brought back to live. Please contact me via indatarec@gmail.com and I will try to help you.


## There are versions of Spark 2 with better and worse audio quality cia using looper
There are at least two versions of Spark 2 motherboard. The ones with 64MB have really bad audio quality using looper and they havo no mark like on the picture below. The better ones have 256/512 mark on them.
<img height="600" alt="looper" src="https://github.com/user-attachments/assets/6bb5ebd9-5c18-40a9-9f3f-026c7a69c44b" />


## Buffer overflow issue
If you would never use Spark app and just save and modify presets on amp, then the flash chip adds new entries, never cleaning old ones. After overflowing flash capacity, Spark 2 does not turn on. You would still do it for a long time to brick Spark 2 like this. This can be fixed.


# Spark 2 MODS


## Speakers reaplce
Spark 40 stock speakers (PSP00471001) in my opinion are medicore at most. If you replace them with anything in range of 20$ speakers, you will hear improvemt. Positive grid says they are angled and FRFR, they are not.
Spark 2 speakers are slighly angled to the sides and they sound a bit better.

## Opamp replace
Spark 2 uses same 3Peak TP2582 opamp as Spark 40, but in more popular SOP8 package so a lot of good can be done here.
<img width="1451" height="900" alt="opamp_spk2" src="https://github.com/user-attachments/assets/3428603e-eb87-4b70-bb0b-7df0eca5e318" />


## other 
tbc 
