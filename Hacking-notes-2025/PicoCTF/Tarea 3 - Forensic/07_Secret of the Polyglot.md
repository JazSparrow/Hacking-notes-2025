# Secret of the Polyglot

#### Description

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf).

#### Hints

* This problem can be solved by just opening the file in different ways.

## Solución

Descargamos el archivo de pdf y lo ubicamos en nuestra carpeta de linux.

Aplicamos un `strings flag2of2-final.pdf | more` y una vez identificado que esta la otra parte de la flag dentro del pdf entonces aplicamos un `cp flag2of2-final.pdf flag2of2-final.png`
y nos transforma nuestro pdf a un png, y nos muestra la otra mitad de nuestra flag.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ file flag2of2-final.pdf
flag2of2-final.pdf: PNG image data, 50 x 50, 8-bit/color RGBA, non-interlaced
jazmin@DESKTOP-1CBQJ6D:~/FSI$ strings flag2of2-final.pdf | more
IHDR
iCCPICC profile
byY%>'
\W<~
C`$G
        pHYs
tIME
tEXtComment
Created with GIMPW
{IDATh
Z@DL
<E3
RJ)ya
% ;@
TvI~
,Ugi
-oF 8
)ZFd{B
::nM/
3"RJE
IEND
%PDF-1.4
%%Invocation: path/gs -P- -dSAFER -dCompatibilityLevel=1.4 -q -P- -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sstdout=? -sOutpu
tFile=? -P- -dSAFER -dCompatibilityLevel=1.4 ?
5 0 obj
<</Length 6 0 R/Filter /FlateDecode>>
stream
oi`inbhd^
endstream
endobj
6 0 obj
endobj
4 0 obj
<</Type/Page/MediaBox [0 0 595 842]
/Rotate 0/Parent 3 0 R
/Resources<</ProcSet[/PDF /Text]
/Font 8 0 R
/Contents 5 0 R
endobj
3 0 obj
<< /Type /Pages /Kids [
4 0 R
] /Count 1
endobj
1 0 obj
<</Type /Catalog /Pages 3 0 R
/Metadata 9 0 R
endobj
8 0 obj
<</R7
7 0 R>>
endobj
7 0 obj
<</BaseFont/Helvetica/Type/Font
/Subtype/Type1>>
endobj
9 0 obj
<</Type/Metadata
/Subtype/XML/Length 1173>>stream
<?xpacket begin='
' id='W5M0MpCehiHzreSzNTczkc9d'?>
<?adobe-xap-filters esc="CRLF"?>
<x:xmpmeta xmlns:x='adobe:ns:meta/' x:xmptk='XMP toolkit 2.9.1-13, framework 1.6'>
<rdf:RDF xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns#' xmlns:iX='http://ns.adobe.com/iX/1.0/'>
<rdf:Description rdf:about="" xmlns:pdf='http://ns.adobe.com/pdf/1.3/' pdf:Producer='GPL Ghostscript 10.01.2'/>
<rdf:Description rdf:about="" xmlns:xmp='http://ns.adobe.com/xap/1.0/'><xmp:ModifyDate>2024-03-12T00:04:30Z</xmp:ModifyD
ate>
<xmp:CreateDate>2024-03-12T00:04:30Z</xmp:CreateDate>
<xmp:CreatorTool>UnknownApplication</xmp:CreatorTool></rdf:Description>
<rdf:Description rdf:about="" xmlns:xapMM='http://ns.adobe.com/xap/1.0/mm/' xapMM:DocumentID='uuid:a5e8afc2-1820-11fa-00
00-d2b2cbb03ca1'/>
<rdf:Description rdf:about="" xmlns:dc='http://purl.org/dc/elements/1.1/' dc:format='application/pdf'><dc:title><rdf:Alt
><rdf:li xml:lang='x-default'>Untitled</rdf:li></rdf:Alt></dc:title></rdf:Description>
</rdf:RDF>
</x:xmpmeta>


<?xpacket end='w'?>
endstream
endobj
2 0 obj
<</Producer(GPL Ghostscript 10.01.2)
/CreationDate(D:20240312000430Z00'00')
/ModDate(D:20240312000430Z00'00')>>endobj
xref
0 10
0000000000 65535 f
0000000563 00000 n
0000001969 00000 n
0000000504 00000 n
0000000363 00000 n
0000000182 00000 n
0000000345 00000 n
0000000656 00000 n
0000000627 00000 n
0000000720 00000 n
trailer
<< /Size 10 /Root 1 0 R /Info 2 0 R
/ID [<75036D3FBE18644DA0C570C5D37A507D><75036D3FBE18644DA0C570C5D37A507D>]
startxref
2095
%%EOF
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cp flag2of2-final.pdf flag2of2-final.png
jazmin@DESKTOP-1CBQJ6D:~/FSI$
```

![[flag2of2-final.png]]

### Respuesta: picoCTF{f1u3n7_1n_pn9_&_pdf_90974127}