# Lab 1 - Rad s diskovima, particijama, datotekama

U sklopu ove vježbe upoznat ćete se sa radom hard diska, pohranom podataka, datotečnim sustavima i particijama. Za realizaciju laboratorijske vježbe, student će dobiti USB kojeg će koristiti za vrijeme lab. vježbi.

## Izrada particija

Vaš zadatak je formatirati USB memoriju te kreirati dvije particije, **NTFS** i **FAT32**. Svakoj particiji je potrebno dati ime koje odgovara vašem imenu ili prezimenu (npr. ime NTFS particije je toni, dok je ime FAT32 particije perkovic). Za realizaciju ove vježbe koristit će se alat **DISKPART** prema uputama kako je navedeno ispod:

1) Otvorite Command Prompt sa administratorskim ovlastima

<br/>
<p align="center">
<img src="figs/cmd_admin.PNG" alt="ECB encryption" width="300px" height="auto"/>
<br><br>
</p>
<br/>



2) upišite `DISKPART` u Command Prompt.

<br/>
<p align="center">
<img src="figs/diskpart.PNG" alt="ECB encryption" width="500px" height="auto"/>
<br><br>
</p>
<br/>


3) Naredbom `list disk` izlistajte diskove na računalu. Uočite disk sa 14 GB, to je USB memorija.

4) Upišite `select disk 1` da biste označili USB disk. Nakon toga upišite naredbu `clean` kako bi izbrisali sve particije koje su kreirane na disku. Nakon toga upišite `create partition primary size=5000` kako biste kreirali novu particiju veličine 5000 MB. Upišite `list volume` kako bi vidjeli što ste dobili.

<br/>
<p align="center">
<img src="figs/diskpart_2.PNG" alt="ECB encryption" width="500px" height="auto"/>
<br><br>
</p>
<br/>

5) Upišite `format fs=ntfs label="toni" quick` kako bi formatirali netom kreiranu **NTFS** particiju. 

6) Sada ćete kreirati **FAT32** particiju. Upišite create `partition primary`. Nakon toga upišite `format fs=fat32 label="toni" quick` te joj dodijelite slovo G:. Za to realizirat, upišite `assign letter="G"`

<br/>
<p align="center">
<img src="figs/diskpart_3.PNG" alt="ECB encryption" width="500px" height="auto"/>
<br><br>
</p>
<br/>

Postupak kreiranja particija i volumena možete napraviti korištenjem [AOMEI Partition Assitant-a](https://www.disk-partition.com/free-partition-manager.html).

## Upravljanje datotekama

Uvjerite se da se na USB-u ne nalazi nikakav sadržaj. Nakon toga kreirajte tekstualnu datoteku (sa ekstenzijom `.txt`) i word datoteku (sa ekstenzijom `.docx`) na obje particije, NTFS i FAT32 te u njih upišite sadržaj. Pitanje:

1) Kolika je fizička veličina datoteke?
2) Kolika je logička veličina datoteke?

> HINT: koristiti `chkdsk` (iz Command Prompt-a sa admin ovlastima), [WinHEX](https://www.x-ways.net/winhex/) alate te `Right click -> Properties` na tekstualnu datoteku kako bi saznali više informacija o datoteci.

