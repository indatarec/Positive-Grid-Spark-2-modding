# Positive-Grid-Spark-2-modding

An article about modding the Positive Grid Spark 2.

The Spark 2 is a major improvement over the Spark 40, with features such as line out, better speakers, and a built-in looper. There are currently two known revisions of the Spark 2 motherboard:

- `"Spark40_GEN2_Main_1.5 2024-06-07 ECB01787"`
- `"Spark40_GEN2_Main_2.1 2024-11-02 ECB02117"` — shown at the top in the picture below.

<img width="2048" height="1152" alt="two_spark2_mobos" src="https://github.com/user-attachments/assets/59ac60f5-35a4-40da-abaa-bcd529fa382b" />
<img height="400" alt="spkmobo1a" src="https://github.com/user-attachments/assets/69ea26a8-1f72-44b9-a06a-3cf4203a8211" />
<img height="400" alt="spkmobo2a" src="https://github.com/user-attachments/assets/3176d4f5-ca7d-4797-af78-e275d2dc22a2" />

It looks like Positive Grid reorganized some components and avoided the cost-cutting seen in later Spark 40 motherboard revisions.

To understand what can be modified and improved, we first need to understand some of the design decisions behind the Spark 2.

---

# Design Considerations of the Spark 2

## Spark 2 Cannot Be Powered by a Power Bank

I often see posts online like this:

https://www.reddit.com/r/PositiveGridSpark/comments/1fgw2qw/higher_capacity_usb_battery_works_with_spark2/

None of the Spark models can negotiate input voltage with a power bank. They do not contain the required power negotiation electronics. Power banks constantly negotiate voltage and current delivery, and voltage drops can occur during use.

The Spark 2 and Spark 40 should not be powered by external power banks, regardless of their specifications. The official Spark battery is the safest and most reliable power solution.

The pictures below show two damaged Spark 2 units caused by power bank usage. Both amps were repairable, and I managed to fix them.

<img height="400" alt="burn2" src="https://github.com/user-attachments/assets/b5cfa247-c5d2-48e6-a6d8-baaf06257233" />
<img height="400" alt="burn1" src="https://github.com/user-attachments/assets/c205614b-53d5-4b5b-b205-ef0f77ccde84" />

---

## MCU Overheating

The main component that requires better cooling in the Spark 2 is the MCU, which runs extremely hot. Unfortunately, improving the cooling solution requires opening the unit and voiding the warranty.

The MCU is cooled using a thin aluminum plate and a low-quality thermal pad, which does not transfer heat efficiently. Cooling of the STM32H750IBK6 chip is one of the weakest points of an otherwise well-designed amp.

<img height="400" alt="mcu" src="https://github.com/user-attachments/assets/f7479f04-f490-4f12-8480-9f3cd66bd853" />
<img height="400" alt="mcu2" src="https://github.com/user-attachments/assets/a433cd1b-b831-4064-9fa0-1f71c6f08ebd" />

---

## Digital Audio Amplifier

In my opinion, the original Spark 40 with the first motherboard revision and a few mods is still the best-sounding amp Positive Grid has made. It uses the analogue TPA3116 amplifier, which has additional headroom and can even be replaced with a 70W TPA3256.

The Spark 2, on the other hand, uses the digital ACM8625P amplifier, which already operates close to its maximum specifications. There is very little room for additional performance tuning.

<img width="746" height="780" alt="amps compare" src="https://github.com/user-attachments/assets/39395fd0-337c-427b-954a-6c108b0d9712" />

The Spark 40 was originally designed as a 2x50W amplifier but was ultimately limited to around 2x20W output. The Spark 2 can deliver around 51W total output at maximum load when using only the guitar input.

That said, the Spark 2 is still a very good evolution of the platform. It offers more features without significantly compromising build quality.

The Spark 2 is like a fast and modern hybrid car.  
The Spark 40 is like an old family car with a hidden V8 engine inside.

<img height="400" alt="amp" src="https://github.com/user-attachments/assets/7e2fcb34-a22e-48f3-a61f-121a099fd9d4" />

---

## Do Not Update Spark 2 Firmware via Wi-Fi or Phone App

The Spark 2 uses an overly complicated firmware flashing process involving both the ESP32 and the MCU.

Updating firmware through the mobile app is risky and can easily brick the device. In my experience, it is one of the most common causes of failed units.

Always update the firmware using a USB cable.

The Bluetooth/app connection is not stable enough for reliable firmware flashing. If the app crashes, disconnects, or is closed in the background during the update process, the Spark 2 may become unbootable.

In many cases the amp can still be recovered. If your Spark 2 becomes bricked, feel free to contact me at `indatarec@gmail.com` and I will try to help.

---

## Different MCU Board Revisions Affect Looper Audio Quality

There are at least two versions of the Spark 2 MCU board.

Boards equipped with 64MB memory have noticeably worse looper audio quality and usually do not include the markings shown in the picture below.

The better revisions are marked with `256` or `512`.

<img height="400" alt="looper" src="https://github.com/user-attachments/assets/6bb5ebd9-5c18-40a9-9f3f-026c7a69c44b" />

---

## Buffer Overflow Issue

If you never use the Spark mobile app and only save or edit presets directly on the amp, the flash memory keeps adding new entries without properly cleaning old ones.

Eventually, the flash storage overflows and the Spark 2 may stop booting.

This takes a long time to happen under normal use, but it is still a firmware issue that can be fixed.

---

# Spark 2 Mods

## Speaker Replacement

In my opinion, the stock Spark 40 speakers (`PSP00471001`) are mediocre at best. Replacing them with almost any decent ~$20 speaker pair results in a noticeable improvement.

Positive Grid markets the speakers as angled and FRFR, but they are not truly FRFR speakers.

The Spark 2 speakers are slightly angled outward and sound somewhat better than the Spark 40 stock speakers.

<img height="400" alt="speakers" src="https://github.com/user-attachments/assets/8e588ec6-da65-4f65-8f92-091bd8ac5666" />

---

## Op-Amp Replacement

The Spark 2 uses the same 3Peak TP2582 op-amp found in the Spark 40, but in the more common SOP-8 package, which makes modifications and replacements much easier.

There is significant room for improvement here.

<img height="400" alt="opamp_spk2" src="https://github.com/user-attachments/assets/3428603e-eb87-4b70-bb0b-7df0eca5e318" />

---

## Other Mods

To be continued.
