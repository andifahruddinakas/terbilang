# Terbilang

Mengubah angka menjadi kata (dan sebaliknya) dalam bahasa Indonesia.

## Pemasangan

Jalankan perintah [composer](http://getcomposer.org)

```bash
composer require akas/terbilang
```

## Penggunaan

Dengan menggunakan helper `terbilang()` and `tersebut()` :

```php
<?php

require 'vendor/autoload.php';

echo terbilang(421); // empat ratus dua puluh satu (string)
echo tersebut('empat ratus dua puluh satu'); // 421.0 (float)
```

Contoh lama:

```php
<?php

require 'vendor/autoload.php';

echo \Nasution\Terbilang::convert(42); // empat puluh dua
echo \Nasution\Terbilang::revert('empat puluh dua');  // 42.0 (float)
```

Anda juga dapat mengimpor kelas agar lebih nyaman digunakan:
```php
<?php

require 'vendor/autoload.php';

use Nasution\Terbilang;

echo Terbilang::convert('123304'); // seratus dua puluh tiga ribu tiga ratus empat
echo Terbilang::revert('seratus dua puluh tiga ribu tiga ratus empat'); // 123304.0 (float)
```

Contoh lain:

```php
echo Terbilang::convert('1000000');          // satu juta
echo Terbilang::convert('1000000000');       // satu milyar
echo Terbilang::convert('1000000000000');    // satu triliun
echo Terbilang::convert('1000000000000000'); // satu kuadriliun


echo Terbilang::revert('satu juta');       // 1000000
echo Terbilang::revert('satu milyar');     // 1000000000
echo Terbilang::revert('satu triliun');    // 1000000000000
echo Terbilang::revert('satu kuadriliun'); // 1000000000000000
echo Terbilang::revert('seratus milyar tiga puluh juta dua puluh ribu sepuluh'); // 100030020010.0
```

Anda juga dapat menggunakan notasi titik pada `Terbilang::convert()` untuk memisahkan angka:

```php
echo Terbilang::convert('1.300.000');       // satu juta tiga ratus ribu
echo Terbilang::convert('100.030.020.010'); // seratus milyar tiga puluh juta dua puluh ribu sepuluh
```
