# odev1-gokalpavcu
Javascript ve Typescript farkı / Node.js ile sunucuyu ayağa kaldırma

1-TypeScript’in Avantajları

TypeScript kolay kod gezinme, hata önleme ve kodun korunmasını sağlar.Statik Tip ek açıklama veya Statik Yazma özelliğini destekler.
Ayrıca arayüzleri, alt arayüzleri, sınıfları, alt sınıfları ve ECMAScript 6 veya ES6’yı destekler.
Özel üyelerin ve arayüzlerin mirası ile nesne yönelimli programlama yetenekleri ile birlikte gelir.
Zengin IDE’ler Mevcuttur

2-JavaScript’in Avantajları

JavaScript, Microsoft ve Mozilla gibi efsanelerin desteklediği açık kaynaklı, esnek ve güçlü bir dildir.
Hem istemci hem de sunucu tarafı için kullanılabilir.
Sınıfları, arayüzleri ve modülleri destekler.
Küçük scriptler için özel olarak tasarlanmıştır.
Platformlar arası bir dil.
Güçlü Test İş Akışı ve bağımlılık desteği sağlar.

JavaScript ve TypeScript Arasındaki Fark

JavaScript, öğrenmesi kolay bir dil iken, TypeScript sert bir öğrenme eğrisine sahip ve önceden komut dosyası bilgisi gerektirir.
TypeScript, derleme zamanında yazım doğruluğunu kontrol etmenizi sağlayan statik Yazma özelliğini desteklerken, JavaScript bunu desteklememektedir.
TypeScript Kodunun derlenmesi gerekiyor ancak JavaScript’i derlemeye gerek yok.
TypeScript isteğe bağlı parametre işlevini destekler, ancak JavaScript desteklemez.
JavaScript’te büyük bir geliştirici topluluğu var, ancak TypeScript yok.
Airbnb, Codecademy ve Instagram JavaScript kullanmasına rağmen, Asana, Clever, Screen award, vb. TypeScript kullanıyor.
JavaScript küçük çaplı projelerde, dinamik web sayfalarında kullanıma yönelik iken TypeScript büyük çaplı projelere yöneliktir.

-----------------------------------------------------Node.js ile sunucuyu ayağa kaldırma-----------------------------------------------------------



İlk olarak bi tane NodeJS projesi oluşturuyoruz. Bunun için de istediğimiz bi yerde bi klasör oluşturup içerisine yine istediğimiz bi isimde javascript dosyası oluşturalım. Örneğin ben index.js adında bi dosya oluşturdum.
Bu javascript dosyası kodlarımızı yazacağımız dosya olacak.
Şimdi terminali (Windows için cmd) açıp oluşturduğumuz klasör içine giriyoruz. Bunun için ya klasörü açıp Linux’ta sağ tıklayıp Terminali aç diyerek ve Windows’ta yine klasörü açıp üstteki adres barına cmd yazarak bulunduğumuz klasörde terminal açabiliriz.
Veyahut terminali açıp Linux ve MacOS için örneğin cd /home/Masaüstü/proje, Windows için ise cd /c:/users/kullanici/desktop/proje komutuyla klasöre girebiliriz.Ardından içinde bulunduğumuz klasör yani projeyi NodeJS projesine çevirmemiz gerek.
Bunun için ise terminalden

1
npm init

komutunu giriyoruz. Npm (NodeJS Package Manager), adından da anlaşılacağı üzere NodeJS projelerini ve projemiz için gerekli olan bağımlılıkları yönetmemizi sağlayan bi yöneticidir.
Komutu girdikten sonra proje adı, proje çalıştırma dosyası gibi bilgileri doldurup projemizi hazır hale getiriyoruz.
Veya npm’nin otomatik olarak bilgileri tanıması için npm init yerine

1
npm init --yes

komutunu girebiliriz.
Evet NodeJS projemizi oluşturduktan sonra server oluşturmaya geçelim.
Server oluşturmak için öncelikle gerekli olan paketi yani ExpressJS’i projemize ekleyelim. Bunun için terminalden

1
npm install express

yazmamız yeterli. Npm, ExpressJS ve onun için gerekli olan tüm bağımlılıkları yükleyecek ve proje dosyalarımız içerisine node_modules adında bi klasör oluşturacaktır.
node_modules klasöründen kısaca bahsetmek gerekirse; NodeJS projemiz için gerekli olan tüm paketler bu klasör içinde toplanır.
Siz yeni bi paket yüklediğinizde eğer istediğiniz paket NodeJS kurarken geldiyse, kurulum dosyaları arasından bu klasör içine kopyalanır. Eğer NodeJS kurulumu sırasında ön tanımlı paketlerden farklı bi paket yüklerseniz, paket node_modules klasörü içine indirilerek projeye dahil edilir.
Evet bu kadar teknik detaydan sonra kaldığımız yerden devam edelim.
Şimdi artık ExpressJS kullanarak server oluşturalım.
Bunun için öncelikle ExpressJS modülünü projemizde çağıralım.
Bildiğiniz üzere NodeJS’de projeye modül dahil etmek için require fonksiyonunu kullanıyoruz. Aynı şekilde ExpressJS modülünü dahil etmek için de

1
const express = require('express');

kod satırını kullanacağız. Fakat ExpressJS modülü class yapısında olduğu için oluşturduğumuz express değişkenini doğrudan kullanamıyoruz. ExpressJS’i tam bi şekilde kullanabilmek için modül içerisinde bulunan class’tan yeni bir nesne türetmemiz gerek.
Bunun için de
1
const app = express()
kod satırını kullanacağız. Bu sayede ExpressJS modülünü sorunsuz bi şekilde kullanabiliriz.Evet ExpressJS modülünü de sorunsuz bi şekilde ekledikten sonra artık server oluşturmaya yarayan kodları yazmaya başlayabiliriz.
Localde çalışan bi server olduğu için bize boş bi tane port gerekiyor. Çünkü serverimiz belirttiğimiz portu dinleyecek ve gelen istekleri cevaplayarak geri cevap gönderecektir.
ExpressJS’in kendi dökümantasyonunda 3000 portunu kullandığı için bizde bunu kullanalım fakat 3000 portunu kullanmak zorunda değiliz, siz isterseniz 5000, 2500 gibi farklı portları da kullanabilirsiniz.Şimdi öncelikle gelen istekleri karşılaşmamız yani router (yönlendirici) oluşturmamız gerekiyor. Bunun içinde
1
2
3
4
app.get('/', (req, res) => {
    res.send('Hello World !');
    res.end();
});
kod satırını kullanacağız.
Yazmış olduğumuz bu kodda / sunucumuzun ana sayfasını temsil ediyor. Yani localhost:3000 adresine tekabül ediyor.
req değişkeni sunucuya gelen istekleri ve res değişkeni de sunucudan geri dönen cevaplara karşılık geliyor.
Yani sunucuya giden istekler req değişkeni, sunucudan geri dönen istekler ise res değişkeni içerisinde saklanıyor.
res.send() fonksiyonu sunucudan gelen cevaplar içine fonksiyona gönderdiğimiz parametreyi ekler ve dönen cevabın o şekilde derlenmesini sağlar.
Yani biz aslında sunucuya istek göndermiyor; sunucudan gelen cevabın arasına eklemeler yapıp, o şekilde derlenip çıktı vermesini sağlıyoruz.
res.end() fonksiyonu ise yapacağımız eklemelerin ve dolayısıyla cevabın tamamlandığını belirtiyor.
Bunu yapmamızın sebebine gelirsek; örneğin Google Chrome tarayıcısı ile bi web sitesine girdiğimizi farzedelim. Sitenin bulunduğu sunucu kendisine gelen istek yani komutları yorumlar (veya derler) ve sonrasında bi tane request açarak elde ettiği sonuçları tarayıcıya gönderir. Request açık olduğu sürece tarayıcı, sunucuyu dinlemeye devam eder ve request tamamlandığında tarayıcı, sonucuyla bağlantıyı koparır ve çıktı üretir.
Işte bizde res.end() fonksiyonu ile requestin tamamlandığını tarayıcıya bildiriyor ve çıktı vermesi için uyarıyoruz.
Eğer requestin tamamlandığını tarayıcıya bildirmezsek sunucudan herhangi bi cevap gelmese bile tarayıcı dinlemeye devam eder ve request tamamlanıp uyarılmadığı için de hiçbir zaman çıktı üretemez. Dolayısıyla sayfa sürekli yükleniyor olarak kalır.Routeri oluşturduk fakat hâlâ sunucuyu aktifleştirmedik, yani bu şekilde derleme yapar ve localhost:3000 adresine giderseniz hata alacaksınız.
Sunucuyu başlatmak için ise;
1
2
3
app.listen(3000, () => {
    console.log('Ilk NodeJS uygulaması 3000 portunda çalışıyor');
});
kod satırını kullanmamız gerek.
listen() fonksiyonu belirtilen portu (3000) dinlemeye başlar.
Fonksiyon içinde bulunan console.log(‘Ilk NodeJS uygulaması 3000 portunda çalışıyor’); kısmı tamamen isteğe bağlıdır, bu kodu kullanmak şart değildir ve isteğe göre de boş bırakılabilir.
Ben sunucunun çalıştığını görebilmek amacıyla kullandım.Şimdi sırada sunucuyu çalıştırmak var. Bunun için terminalde
1
node index.js
komutunu giriyoruz. Bu komut sayesinde projemizi çalıştırıyoruz. Evet artık sunucumuz sorunsuz bir şekilde çalışıyor olacaktır. localhost:3000 adresine gittiğimizde ekranda Hello World ! yazdığını göreceksiniz.
Fakat şöyle bir sorun var; localhost:3000 içinde kalmak şartıyla hangi adrese giderseniz gidin karşınıza Hello World ! yazısı çıkacaktır. Çünkü biz sadece / ile başlayan adresleri kontrol ettik ve yönlendirdik. Örneğin localhost:3000/kategoriler adresi için de ayrıca bi yönlendirme yapmak istersek;

1
2
3
4
app.get('/kategoriler', (req, res) => {
    res.send('<h1>Kategoriler Sayfasına Hoşgeldiniz<h1>');
    res.end();
});

kodunu ekleyerek kategoriler sayfasi içinde ayrıca bi router oluşturmamız gerekiyor. res.send() fonksiyonu içerisine illa ki metin yazmak zorunda değiliz, HTML kodu da ekleyebilirsiniz.Fakat bu routeri sunucuyu başlatmadan öncesine eklememiz gerekiyor. Çünkü sunucu başlatıldıktan sonraki routerler geçersiz olur ve çalışmaz.Router sayısını istediğiniz kadar arttırabilirsiniz; 100 tane sayfanız varsa 100 tane router yazabilirsiniz.
Evet NodeJS ile ExpressJS kullanarak server oluşturma işlemimiz tamamlandı ve artık sunucumuz başarıyla çalışıyor.
