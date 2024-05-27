# DAQ systems

- [DAQ system](#daq-system)
- [Design of measuring chain](#design-of-measuring-chain)
- [ASSD](#assd)
- [DCS](#dcs)


## DAQ system
- **Data acquisition -system sber dat** is the process of **sampling(vzorkovani -  vznik diskrétních signálů ze signálů spojitých) signals** that measure real-world physical conditions and converting the resulting samples into digital numeric values that can be manipulated by a computer.
- Typically convert **analog waveforms into digital values for processing.**
- The components of data acquisition systems include:
  - **Sensors**, to convert physical parameters(fyzikální nebo technickou veličinu) to electrical signals. **Nejčastěji jde o elektrický signál (časový průběh napětí nebo proudu)**
  - **Signal conditioning circuitry**, is the manipulation of **an analog signal in such a way that it meets the requirements of the next stage for further processing.**
    - In an **analog-to-digital converter (ADC) application**, signal conditioning includes **voltage or current limiting** and **anti-aliasing filtering.**
    - It is common to have **a sensing stage (which consists of a sensor)**, **a signal conditioning stage (where usually amplification- zesilovač slouží především k zesílení amplitudy signálu, nebo jeho úrovně (u stejnosměrných zesilovačů), na požadovanou hodnotu. Používá se ale i v zapojeních, kde je potřeba změnit tvar signálu - tranzistor,  of the signal is done)** and a processing stage (**often carried out by an ADC and a micro-controller**).
    - Signal amplification performs two important functions: **increases the resolution of the input signal**, and increases its signal-to-noise ratio
    -  the output of an electronic temperature sensor, which is probably in the millivolts range is probably too low for an analog-to-digital converter (ADC) to process directly.
  - **Analog-to-digital converters**, to convert conditioned sensor signals to digital values.
 
## Design of measuring chain
- merici retezec
- **Měřicím řetězcem** rozumíme **sled jednotlivých prvků** mezi snímačem, který je prvním článkem řetězce a vyhodnocovacím zařízením, které je jeho posledním článkem
- Výstupem z převodníku nebo z vysílače bývá často **tzv. unifikovaný signál**, který se pohybuje v přesně definovaném rozmezí. Např. **proudový signál 0 až 20 mA, nebo 4 až 20 mA**, **napěťový signál 0 až 10 V nebo -10 až +10 V**, pneumatický signál 20 až 100 kPa.


## ASSD
- **automatizovany system sberu dat**
- Hlavní komponenty automatizovaného systému sběru dat:
  - **1. Senzory a měřicí zařízení**:
    - Zařízení, která detekují **fyzikální nebo chemické jevy a převádějí je na elektrické signály**. Příklady zahrnují teplotní senzory, tlakové senzory, senzory vlhkosti, světelné senzory, atd.
    - **Měřicí zařízení:** Přístroje, které měří specifické parametry, jako jsou multimetery, osciloskopy, analyzátory plynů, atd.
  - **2. Převodníky (A/D a D/A):**
  - **3. Sběrače, Ukladac dat (Data Loggers):**
  - **4. Komunikační rozhraní:**
    - Drátová: **RS-232, RS-485, Ethernet, USB, atd.**
    - Bezdrátová: Wi-Fi, Bluetooth, **ZigBee, LoRa, mobilní sítě (GSM, LTE), atd.**
  - **5. Úložné a databázové systémy:**
    - Lokální úložiště: Paměťová karta, pevný disk, SSD.
    - Cloudové úložiště: Služby jako AWS, Google Cloud, Azure poskytují vzdálené ukládání a zpracování dat.
  - **6. Zpracování a analýza dat:**
    - **Filtrace šumu**
      - Při měření teploty pomocí senzorů může dojít k šumu způsobenému elektromagnetickými interferencemi nebo kolísáním napětí. Jednoduchý **pohyblivý průměr může být použit k vyhlazení dat**
      - **Klouzavý průměr je průměr sousedních pozorování časové řady**. Jedná se o elementární metodu, jak odhadnout **trend časové řady**. Počítá se jako průměr konstantního počtu za sebou jdoucích období. Pomocí klouzavého průměru se křivka vyhladí a lze lépe určit trend nebo změnu trendu.
    - **Detekce anomálií**
      - **Detekce výkyvů v průmyslových strojích:** Algoritmy pro detekci anomálií mohou identifikovat neobvyklé vzory v datech
    - **Agregace dat**
      - Sledování spotřeby energie
  - **7. Řídicí systémy**:
    - **PLC (Programmable Logic Controllers)**: Programovatelné logické automaty používané v průmyslu pro řízení procesů.
    - **SCADA (Supervisory Control and Data Acquisition)**: dispečerské řízení a sběr dat.
      - je provozován **na vyšší úrovni nad prostředky procesní automatizace** (např. PLC automaty, I/O moduly, dataloggery, senzory, čítače, měřiče ..), které zodpovídají za řízení, konektivitu a sběr dat ze sledovaných technologických procesů.       
     
## DCS
- distributed control system
- **control system** for a process  usually with many **control loops - ridici smycka**, in which **autonomous controllers are distributed throughout the system**, but there is **no central operator supervisory control**
- This is in contrast to systems that use **centralized controllers**: either discrete controllers located at a central control room or within a central computer. 
- Today the functionality of (SCADA) and DCS systems are very similar, but **DCS tends to be used on large continuous process plants** where high reliability and security is important

- The accompanying diagram is a general model which shows functional manufacturing levels using computerised control:
  - Level 0 - **Field level**: contains the field devices such as **flow and temperature sensors**, and final control elements, such as control valves - ridici ventil
  - Level 1 - **Direct control**: contains the **industrialised Input/Output (I/O) modules**, and their associated distributed electronic processors.
  - Level 2 - **Plant Supervisory**: contains the supervisory computers, which collect information from processor nodes on the system, and provide the operator control screens.
  - Level 3 - **Production control**: is the production control level, which does not directly control the process, but is concerned with monitoring production and monitoring targets
  - Level 4- **Production Scheduling**: is the production scheduling level.

- **Levels 1 and 2 are the functional levels of a traditional DCS**, in which **all equipment are part of an integrated system from a single manufacturer.**
- Levels 3 and 4 are not strictly process control in the traditional sense, but where production control and scheduling takes place. 


 
