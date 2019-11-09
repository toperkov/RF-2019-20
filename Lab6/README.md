# Lab 6 - Windows Registry i Event log

U sklopu današnje vježbe analizirat ćemo Windows Registry u svrhu forenzične analize. Cilj ove vježbe je saznati vrijeme kada je posljednji put bilo ugašeno računalo, kada i koji USB uređaj je bio priključen na računalo, listu svih pristupnih točaka na koje je računalo bilo povezano u prošlosti, itd. Također ćemo se upoznati sa analizom Event Loga na Windowsima.

## Windows registry

1. Iz windows registry-a saznajte kada je posljednji put bilo ugašeno računalo.

>> **HINT:** HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Windows
Upotrebljavajte DCode iz Digital Detective kako biste dekodirali vrijeme.


2. Napravite popis svih USB uređaja koji su bili povezani na računalo u prošlosti.
>> **HINT:** Koristite [USBDeview](https://www.nirsoft.net/utils/usb_devices_view.html) i [USB Forensic Tracker](http://www.orionforensics.com/downloads/usb-forensic-tracker/)

3. Anti-forenzika: Izbrišite popis svih USB uređaja iz Windows registry-a korištenjem programa [USB Oblivion](https://sourceforge.net/projects/usboblivion/)

4. Ispišite listu svih pristupnih točaka na koji je bio povezano vaše računalo. Navedite kada se prvi put povezalo na računalo i posljednji put.
>> **HINT:** SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList

5. Navedite listu svih programa koji su bili pokrenuti na vašem računalu unazad 10 dana. Pri tome možete koristiti [WinPrefetchView](http://www.nirsoft.net/utils/win_prefetch_view.html) iz Nirsoft-a.


6. Koristite Windows Thumbnail Forenziku kako biste saznali popis posljednje otvorenih dokumenata
>> **HINT:** %userprofile%\AppData\Local\Microsoft\Windows\Explorer


7. Jump Lists Forenzika. Za analizu aktivnosti korisnika na računalu navedite datoteke kojima je zadnji put pristupljeno
>> **HINT:** \Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\ 


## Analiza Event Loga

1. U Even viewer-u saznajte pod Windows Logs -> System saznajte vrijeme kada je posljednji put računalo bilo ugašeno i kada te kada je resetirano.

