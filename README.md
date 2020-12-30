# Tutorial List Spinner
Bagaimana merubah bentuk list ini : [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

Menjadi bentuk list seperti ini : [[3, 6, 9], [2, 5, 8], [1, 4, 7]]

<hr>
<hr>

## *__STEP 1__*
__Mencari Kombinasi Indeks List Yang Akan Dibuat Terhadap Urutan List Lama__
<hr>



Kombinasi Indeks List yang akan dibuat terhadap urutan list lama ialah sebagai berikut :

[[0][2], [1][2], [2][2]], 

[[0][1], [1][1], [2][1]], 

[[0][0], [1][0], [2][0]]

```
List_awal = [
            [1, 2, 3], 
            [4, 5, 6], 
            [7, 8, 9]
            ]

h = [                                     # Inisiasi Awal List (Template List Tujuan)
    [0, 0, 0], 
    [0, 0, 0], 
    [0, 0, 0]
    ]

i0 = 0                                    # Keterangan iterasi ke-i

i1 = 0                                    # indeks primer   (i)

i2 = 2                                    # indeks sekunder (j)

while True:                               # Start Iterasi
    print(f"===== Iterasi {i0}=====")     # Keterangan Iterasi ke-i
    i0 += 1                               # Update ke Keterangan Iterasi ke-i
    print (i1,i2)                         # Pengecekan indeks primer(i) dan indeks sekunder(j)
    i1 += 1                               # Update indeks primer (i)

    if  i1 == len(h):                     # Kondisi indeks primer (i) harus berhenti
        i1  = 0                           # Mendefenisikan  primer (i) kembali bernilai 0
        i2 -= 1                           # Update indeks primer dikurang 1 (j)

        if i2 < 0:                        # Kondisi indeks Sekunder (j) harus berhenti
            break
```
_Output :_

![Output Step 1](https://user-images.githubusercontent.com/74448921/103364618-34517d80-4af9-11eb-9b65-39913e220f31.jpg)

<hr>
<hr>

## *__STEP 2__*
__Menyesuaikan kombinasi indeks di inisiasi list awal terhadap indeks list yang akan dibuat__


<hr>


Kombinasi Indeks Template List yang akan dibuat terhadap urutan list tujuan ialah sebagai berikut :

[[0][0], [0][1], [0][2]], 

[[1][0], [1][1], [1][2]], 

[[2][0], [2][1], [2][2]]
```
List_awal = [
            [1, 2, 3], 
            [4, 5, 6], 
            [7, 8, 9]
            ]
h = [
    [0, 0, 0], 
    [0, 0, 0], 
    [0, 0, 0]
    ]

i0 = 0
i1 = 0                              
i2 = 2                              
i3 = 0                                           # indeks primer   (i, Template List  (variabel h))
i4 = 0                                           # indeks sekunder (j, Template List  (variabel h))
while True: 
    print(f"===== Iterasi {i0}=====")  
    i0 += 1                      
    print ("List Tujuan = ", i1, i2)             # Keterangan untuk List Tujuan  
    print ("Template List Tujuan = ", i4, i3)    # Keterangan untuk Template List Tujuan
    i1 += 1                               
    i3 += 1                                      # update indeks sekunder (Template List Tujuan)


    if  i1 == len(h) and i3 == len(List_awal):   # (opsional) menambahkan kondisi i3 jika sudah bernilai 2 (harus stop)        
        i1 = 0 
        i3 = 0                                   # meng 0 kan indeks sekunder kembali           
        i4 += 1                                  # update indeks primer 
        i2 -= 1                                       


        if i2 < 0 and i4 == len(List_awal):      # (opsional) menambahkan Kondisi indeks i4 jika sudah bernilai 2 (harus stop)                           
          break    
```         

_Output :_

![Output Step 2](https://user-images.githubusercontent.com/74448921/103367717-cc9f3080-4b00-11eb-88ac-adc4b702db52.jpg)

<hr>
<hr>

## *__STEP 3__*
__Mengeluarkan Hasil dan finalisasi__

<hr>

<br>

```
def List_Spinner(List_awal):
  h = [
      [0, 0, 0], 
      [0, 0, 0], 
      [0, 0, 0]
      ]
  i1 = 0                              
  i2 = 2                              
  i3 = 0    
  i4 = 0    
  while True:                      
      h[i4][i3] = List_awal[i1][i2]                # Melakukan Replace Template List Tujuan dengan List Tujuan
      i1 += 1                               
      i3 += 1 
      if  i1 == len(h) and i3 == len(h):           
          i1 = 0 
          i3 = 0                                      
          i4 += 1                           
          i2 -= 1                                       

          if i2 < 0 and i4 == len(h):                                 
            x = h                                   # Keluarin nilai
            break                                     
  return x

x = [[1, 2, 3], 
    [4, 5, 6], 
    [7, 8, 9]]
print(List_Spinner(x))
```
_Output_

![Output Step 3](https://user-images.githubusercontent.com/74448921/103368494-9bbffb00-4b02-11eb-8500-4c9f6b769733.jpg)

<br>

# Terima Kasih 😊
