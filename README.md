# webservice - XML & DTD

        <!DOCTYPE logbarang SYSTEM "logbarang.dtd">

1. DTD diawali dengan <! DOCTYPE pembatas atau delimiter.
2. logbarang sebagai nama root elemen
3. logbarang.dtd sebagai identifier untuk pengidentifikasi untuk definisi jenis dokumen, dan menjadi path atau jalan ke file di sistem, jika DTD menunjukan path eksternal, maka itu disebut subset eksternal.

Untuk tugas kali ini, saya memakai DTD eksetrnal, jadi DTD dideklarasikan diluar file XML, file ini diaksse dengan menentukan atribut sistem yang berupa file .dtd. Untuk mereferensikan itu sebagai DTD eksternal, atribut yang stand alone atau berdiri sendiri di pada pendeklarasian XML harus di atur 'no'.

            <?xml encoding="UTF-8"?>

    <!ELEMENT logbarang (barang)+> // ELEMENT berarti tag deklarasi elemen. sedangkan loogbarang adalah nama elemennya, dan barang adalah elemen dan setiap elemen harus memiliki pendeklarasian sendiri pada DTD.
    <!ATTLIST logbarang // atribut DTD dimulai pada baris ini, jika elemen mengandung atribut.
        xmlns CDATA #FIXED ''> // pada baris ini menggunakan kata kunci #fixed, dimana hal inin menunjukan bahwa nilai untuk nama atribut dari elemen <barang>

    <!ELEMENT barang (kode,satuan,harga,asal,tujuan)> // pada baris ini, barang adalah elemen induk, sedangkan kode, satuan, harga, asal, dan tujuan adalah anak elemen.
    <!ATTLIST barang //attribut list dari elemen barang
        xmlns CDATA #FIXED ''> // pada baris ini menggunakan kata kunci #fixed, dimana hal ini menunjukan bahwa nilai untuk nama atribut dari elemen <kode,satuan,harga,asal,tujuan> tetap, CDATA adalah teks yang tidak akan bisa parsed oleh parser, tag didalam teks tidak akan diperlakukan sebagai markup dan entitinya tidak akan membesar/meluas.

    <!ELEMENT kode (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
    <!ATTLIST kode //attribut list dari elemen kode
        xmlns CDATA #FIXED ''> // pada baris ini menggunakan kata kunci #fixed, dimana hal ini menunjukan bahwa nilai untuk elemen bersifat tetap.
    <!ELEMENT satuan (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
    <!ATTLIST satuan //attribut list dari elemen satuan
        xmlns CDATA #FIXED ''> // pada baris ini menggunakan kata kunci #fixed, dimana hal ini menunjukan bahwa nilai untuk elemen bersifat tetap.

    <!ELEMENT harga (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
    <!ATTLIST harga //attribut list dari elemen harga
    xmlns CDATA #FIXED // // pada baris ini menggunakan kata kunci #fixed, dimana hal ini menunjukan bahwa nilai untuk elemen bersifat tetap.
    cur CDATA #IMPLIED ''> // pada baris ini menggunakan kata kunci #IMPLIED, dimana hal ini menunjukan bahwa nilai untuk elemen bersifat optional, CDATA adalah teks yang tidak akan bisa parsed oleh parser, tag didalam teks tidak akan diperlakukan sebagai markup dan entitinya tidak akan membesar/meluas.

    <!ELEMENT asal (pt,kodewil)> // pada baris ini, asal adalah elemen induk, sedangkan pt dan kodewil adalah anak elemen.
    <!ATTLIST asal //attribut list dari elemen asal
        xmlns CDATA #REQUIRED ''> // pada baris ini menggunakan kata kunci #REQUIRED, dimana hal ini menunjukan bahwa nilai untuk nama atribut dari elemen (pt,kodewil) bersifat wajib, CDATA adalah teks yang tidak akan bisa parsed oleh parser, tag didalam teks tidak akan diperlakukan sebagai markup dan entitinya tidak akan membesar/meluas.

    <!ELEMENT tujuan (pt,kodewil)> // pada baris ini, asal adalah elemen induk, sedangkan pt dan kodewil adalah anak elemen
    <!ATTLIST tujuan //attribut list dari elemen tujuan
        xmlns CDATA #REQUIRED ''> // pada baris ini menggunakan kata kunci #REQUIRED, dimana hal ini menunjukan bahwa nilai untuk nama atribut dari elemen (pt,kodewil) bersifat wajib, CDATA adalah teks yang tidak akan bisa parsed oleh parser, tag didalam teks tidak akan diperlakukan sebagai markup dan entitinya tidak akan membesar/meluas.

    <!ELEMENT pt (#PCDATA)>
    <!ATTLIST pt //attribut list dari elemen pt
        xmlns CDATA #FIXED ''> // pada baris ini menggunakan kata kunci #fixed, dimana hal ini menunjukan bahwa nilai untuk elemen bersifat tetap.

    <!ELEMENT kodewil (#PCDATA)>
    <!ATTLIST kodewil //attribut list dari elemen kodewil
        xmlns CDATA #REQUIRED ''> // pada baris ini menggunakan kata kunci #REQUIRED, dimana hal ini menunjukan bahwa nilai elemen kodewil bersifat wajib, CDATA adalah teks yang tidak akan bisa parsed oleh parser, tag didalam teks tidak akan diperlakukan sebagai markup dan entitinya tidak akan membesar/meluas.

    
    
  REFERENSI:
    http://www.w3ii.com/xml/default.html
    
    Restiyana Dwi Astuti (1154077) D4 TI 2B
