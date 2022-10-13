
![Logo](https://paratim.com/asset/images/logo.png)

    



# Paratim Iframe Sanal POS entegrasyonu 

ParaTim tarafından yayınlanmış olan Iframe Sanal Pos ekranını daha kolay bir şekilde gerçekleştirmenize imkan tanıyan "IframePayment"  ait dosyalarını kullanmaya başlayabilirsiniz.




## Başlarken 

-Iframe Pos kullanabilmeniz için öncelikle [Paratim.com](https://www.paratim.com/) onaylı bir kullanıcı olmanız gerekmektedir.

-Kullanıcı onayınızın sonrasında Iframe Pos ekranında bulunan bazı sabit güvenlik değişkenleri ve IP & Alan Adı onayını almalısınız.

    
## Iframe Pos Kullanımı

#### Değişkenler

```
    $postUrl="https://api.dev.paratim.com.tr/dealer/iframePayment/getIframeUrl";
    $postData = [
		'merchantId' => $merchantId,
		'subMerchantId' => $subMerchantId,
		'session_token' => $session_token,
		'totalAmount' => $totalAmount,
	  	'currency' => $currency,
		'products' => $products
	];
```

| Parametre | Tip     | Açıklama                |
| :-------- | :------- | :------------------------- |
| `$merchantId` | `INT` | **Gerekli**. Üye işyeri numaranız (İ-Şube'ye giriş yaparken kullandığınız "Temsilci No" değeri) |
| `$subMerchantId` | `INT` | **Gerekli**. Alt Üye İşyeri yönetimi sayfanızda eklediğiniz mağazanın numarası. |
| `$session_token` | `VARCHAR` | **Gerekli**. Entegrasyon adımları anında türettiğiniz "Gizli Token" |
| `$totalAmount` | `FLOAT` | **Gerekli**. Sepetin toplam ödeme tutarı (Aşağıda eklenmiş ürünlerin toplam tutarıdır. Fakat Paratim ürün tutarlarını toplayarak sağlamasını yapmaz. Bu toplam değer üzerinden ödemeye devam eder.). |
| `$currency` | `VARCHAR` | **Gerekli**. gönderilen para birimi. |
| `$products` | `ARRAY` | **Gerekli**.  Ödemesi yapılacak ürünlerin bilgilerini tutacak diziyi tanımladık (Müşterinizin sepetinde bulunan ürünler) |
| `$postUrl` | `INT` | **Gerekli**. iframe içinde kullanacağımız src adresini bize söyleyen Paratim post adresi |

  
## Demo Kart

Iframe Payment Ekranını PreProd ortamında doğruluk testi yapabilmeniz için aşağıdaki Test kartını kullanabilirsiniz.

```bash
    Test kart bilgileri;
    Kart Numarası (Visa) : 4531444531442283
    Kart Numarası (Master Card) : 5818775818772285
    Son Kullanma Tarihi : 12/26
    Güvenlik Numarası : 001
    Kart 3D Secure Şifresi : a
```

  
## Lisans


[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)

  
