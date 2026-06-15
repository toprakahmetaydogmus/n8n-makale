# n8n ile Otomasyon Dünyasına Giriş: Sıfırdan İleri Seviyeye Kapsamlı Rehber

**Hazırlayan: Toprak Ahmet Aydoğmuş — Siber Akademi**

---

## Giriş: Bu Rehber Kime Hitap Ediyor?

Eğer "otomasyon" kelimesini duyduğunuzda akla hemen karmaşık kod satırları, yazılım mühendisleri ve anlaşılmaz terimler geliyorsa, bu rehber tam size göre. Bilgisayar mühendisi olmanıza, kodlama bilmenize ya da "API" kelimesinin ne anlama geldiğini bilmenize gerek yok. Sıfırdan başlayıp, adım adım, hiçbir şeyi atlamadan, gerçek hayattan örneklerle n8n'in ne olduğunu, nasıl kurulduğunu, nasıl kullanıldığını ve günlük hayatınızda ya da işinizde nasıl mucizevi şekilde zaman kazandırabileceğini anlatacağız.

Bu rehberi okuduktan sonra, e-postalarınızı otomatik olarak düzenleyen, sosyal medya hesaplarınızı otomatik besleyen, müşteri taleplerini otomatik yöneten, hatta kahve makinenizi (evet, doğru okudunuz) tetikleyebilen sistemler kurabilecek seviyeye geleceksiniz. Hazırsanız başlayalım.

---

## Bölüm 1: Otomasyon Nedir? Neden Hayatımıza Bu Kadar Çok Girdi?

### 1.1 Günlük Hayattan Bir Örnekle Başlayalım

Diyelim ki her sabah işe gitmeden önce şu işleri yapıyorsunuz:

1. Telefonunuzu açıyorsunuz
2. Hava durumuna bakıyorsunuz
3. E-postalarınızı kontrol ediyorsunuz
4. Önemli olanları ayrı bir klasöre taşıyorsunuz
5. Takım arkadaşlarınıza günün planını bir mesaj olarak gönderiyorsunuz
6. Sosyal medya hesaplarınızdan birine günün ilk paylaşımını yapıyorsunuz

Bu işlemlerin her biri tek tek ele alındığında basit gibi görünür ama hepsini her gün, manuel olarak, tek tek yapmak hem zaman alır hem de can sıkıcıdır. Peki ya bu adımların **hepsini otomatik olarak, siz uyurken bile çalışan bir sistem** yapsa?

İşte otomasyon tam olarak bunu sağlar: **"Eğer şu olursa, şunu yap"** mantığıyla çalışan, insan müdahalesi olmadan tekrar eden görevleri kendi başına gerçekleştiren sistemler kurmaktır.

### 1.2 Otomasyonun Temel Mantığı: Tetikleyici ve Aksiyon

Her otomasyonun iki temel parçası vardır:

**Tetikleyici (Trigger):** "Ne zaman" sorusuna cevap verir. Örneğin:
- Her gün sabah 08:00'de
- Bir e-posta geldiğinde
- Bir form doldurulduğunda
- Bir dosya yüklendiğinde
- Bir web sitesinde fiyat değiştiğinde

**Aksiyon (Action):** "Ne yapılacak" sorusuna cevap verir. Örneğin:
- Bir mesaj gönder
- Bir tabloya satır ekle
- Bir e-posta yolla
- Bir dosya oluştur
- Bir API'ye veri gönder

Otomasyon, basitçe bu iki şeyi birbirine bağlamaktır: **"X olduğunda, Y'yi yap."**

### 1.3 Otomasyon Neden Bu Kadar Popüler Oldu?

Son yıllarda şirketler ve bireyler, tekrar eden, "düşünmeye gerek olmayan ama zaman alan" işlerin yapay zeka ve otomasyon araçlarıyla devredilebileceğini fark ettiler. Bu durum üç ana sebepten kaynaklanıyor:

**Birincisi**, dijital araçların sayısı patladı. Artık herkesin kullandığı onlarca farklı uygulama var: e-posta, takvim, CRM (müşteri yönetim sistemleri), sosyal medya, ödeme sistemleri, depolama servisleri, mesajlaşma uygulamaları... Bu kadar çok aracın hepsini elle yönetmek mümkün değil.

**İkincisi**, bu araçların çoğu birbirleriyle "konuşabiliyor". Yani bir uygulamadan veri alıp başka bir uygulamaya gönderebiliyorsunuz — buna teknik olarak **entegrasyon** denir.

**Üçüncüsü**, yapay zeka (özellikle ChatGPT, Claude gibi dil modelleri) artık otomasyonların içine entegre edilebiliyor. Bu da otomasyonları sadece "mekanik" işler için değil, "düşünme gerektiren" işler için de kullanılabilir kılıyor. Örneğin gelen bir müşteri e-postasını yapay zeka okuyup, hangi departmana yönlendirilmesi gerektiğine karar verebiliyor — tamamen otomatik.

### 1.4 Otomasyon Araçlarına Genel Bir Bakış

Piyasada birçok otomasyon aracı var. En bilinenleri şunlardır:

- **Zapier**: Kullanımı çok kolay ama ücretli planları pahalı, özelleştirme imkanı sınırlı.
- **Make (eski adıyla Integromat)**: Görsel ve güçlü, ama abonelik bazlı ve karmaşık akışlarda maliyet artıyor.
- **n8n**: Açık kaynaklı (yani kodu herkese açık ve ücretsiz kullanılabilir), kendi sunucunuzda barındırabiliyorsunuz, sınırsız otomasyon kurabiliyorsunuz ve hem görsel hem kod tabanlı çalışabiliyor.

İşte bu rehberde **n8n**'i seçtik çünkü:

1. **Ücretsiz** olarak kendi bilgisayarınızda veya bir sunucuda çalıştırabilirsiniz.
2. **Sınırsız otomasyon** kurabilirsiniz (Zapier gibi "aylık 100 işlem" sınırı yok).
3. **Görsel arayüzü** sayesinde kod yazmadan, sürükle-bırak mantığıyla otomasyon kurabilirsiniz.
4. Gerekirse **JavaScript kodu** da yazabilirsiniz — yani ileri seviyede sınırsız özelleştirme imkanı sunar.
5. **400'den fazla uygulama** ile hazır entegrasyonu var (Gmail, Telegram, Slack, Google Sheets, Notion, WhatsApp ve daha fazlası).
6. Yapay zeka modelleri (OpenAI, Claude, Ollama gibi) ile doğrudan entegre olabilir.

---

## Bölüm 2: n8n Nedir? Detaylı Tanıtım

### 2.1 n8n'in Hikayesi

n8n ("nodemation" kelimesinden geliyor, "n-8-n" şeklinde okunur — aradaki 8 harf "odematio" kelimesinin kısaltmasıdır) Almanya merkezli bir şirket tarafından geliştirilen açık kaynaklı bir iş akışı otomasyon platformudur. "Açık kaynak" demek, yazılımın kodunun herkese açık olduğu ve isteyen herkesin onu inceleyebildiği, değiştirebildiği, kendi sunucusunda çalıştırabildiği anlamına gelir.

n8n'in en büyük avantajı, **"fair-code"** lisansı altında dağıtılmasıdır. Bu, kişisel veya iç kullanım için tamamen ücretsiz olduğu, ama eğer n8n'i bir ürün haline getirip başkalarına satmak isterseniz lisans almanız gerektiği anlamına gelir. Bizim gibi bireysel kullanıcılar veya küçük işletmeler için bu pratikte **tamamen ücretsiz** demektir.

### 2.2 n8n ile Ne Yapabilirsiniz? Gerçek Hayat Örnekleri

Hayal gücünüzün sınırları kadar çok şey yapabilirsiniz, ama işte size somut, gerçek hayatta kullanılan örnekler:

**Örnek 1 - E-posta Yönetimi:**
Gmail'inize gelen her e-postayı otomatik olarak okuyup, içeriğine göre (fatura, şikayet, teklif, spam vb.) farklı klasörlere taşıyabilir, önemli olanlar için size Telegram'dan bildirim gönderebilirsiniz.

**Örnek 2 - Sosyal Medya Yönetimi:**
Bir Google Sheets dosyasına yazdığınız içerikleri, belirlediğiniz tarih ve saatlerde otomatik olarak Instagram, Twitter (X) veya LinkedIn'de paylaşabilirsiniz.

**Örnek 3 - Müşteri Takibi (CRM):**
Web sitenizdeki bir formu doldurulduğunda, o kişinin bilgilerini otomatik olarak bir Google Sheets'e veya bir CRM sistemine ekleyebilir, aynı zamanda o kişiye otomatik bir "hoş geldiniz" e-postası gönderebilir ve satış ekibinize Slack üzerinden bildirim yollayabilirsiniz.

**Örnek 4 - Fiyat Takibi:**
Beğendiğiniz bir ürünün fiyatını her gün otomatik kontrol edip, fiyat düştüğünde size WhatsApp mesajı gönderen bir sistem kurabilirsiniz.

**Örnek 5 - Yapay Zeka Destekli Müşteri Hizmetleri:**
Web sitenize gelen müşteri mesajlarını otomatik olarak yapay zekaya (örneğin Claude veya ChatGPT) gönderip, yapay zekanın verdiği cevabı otomatik olarak müşteriye iletebilirsiniz.

**Örnek 6 - Fatura ve Muhasebe:**
Gelen fatura e-postalarındaki PDF'leri otomatik olarak indirip, bir Google Drive klasörüne kaydedip, aynı zamanda bir muhasebe tablosuna otomatik kayıt girebilirsiniz.

**Örnek 7 - İçerik Üretimi:**
Bir RSS kaynağından (haber sitesi gibi) yeni bir içerik geldiğinde, bu içeriği yapay zekaya özetletip, özet halini bir Telegram kanalına otomatik gönderebilirsiniz.

**Örnek 8 - Yedekleme:**
Belirli aralıklarla veritabanınızın yedeğini alıp, otomatik olarak bir bulut depolama servisine (Google Drive, Dropbox vb.) yükleyebilirsiniz.

Gördüğünüz gibi, n8n'in kullanım alanları sınırsız. Önemli olan, "bu işi her zaman aynı şekilde, tekrar tekrar yapıyorum" dediğiniz her görevi otomatikleştirebileceğinizi anlamaktır.

### 2.3 n8n'in Temel Kavramları: Sözlük

n8n öğrenirken karşınıza çıkacak temel terimleri burada açıklayalım. Bu terimleri bir kere öğrendiğinizde, rehberin geri kalanını çok daha rahat takip edeceksiniz.

**Workflow (İş Akışı):** Bir otomasyonun tüm yapısına verilen isimdir. Bir workflow, birbirine bağlı "node"lardan (düğümlerden) oluşur. Örneğin "Her sabah hava durumunu kontrol et ve mesaj gönder" işleminin tamamı bir workflow'dur.

**Node (Düğüm):** Bir workflow içindeki her bir "kutucuk"tur. Her node bir işlem yapar: veri çeker, veri gönderir, veriyi dönüştürür, bir koşulu kontrol eder vb. Node'lar birbirine çizgilerle bağlanır ve veri bu çizgiler üzerinden akar.

**Trigger Node (Tetikleyici Düğüm):** Bir workflow'un nasıl başlayacağını belirleyen özel node türüdür. Her workflow'da en az bir tetikleyici node bulunmalıdır. Örnekler: "Manuel Tetikleme" (siz butona bastığınızda çalışır), "Zamanlama" (belirli saatlerde çalışır), "Webhook" (bir sistemden veri geldiğinde çalışır).

**Action Node (Aksiyon Düğümü):** Tetikleyici çalıştıktan sonra sırayla işlem yapan node'lardır. Örneğin "Gmail'e e-posta gönder", "Google Sheets'e satır ekle" gibi.

**Connection (Bağlantı):** Node'lar arasındaki çizgilerdir. Bu çizgiler verinin nereden nereye akacağını gösterir.

**Execution (Çalıştırma):** Bir workflow'un bir kez çalıştırılmasıdır. Her çalıştırmanın geçmişi n8n tarafından kaydedilir, böylece hangi verinin nasıl işlendiğini sonradan inceleyebilirsiniz.

**Credential (Kimlik Bilgisi / Bağlantı Anahtarı):** n8n'in başka bir servise (Gmail, Telegram, Google Sheets vb.) bağlanabilmesi için gereken giriş bilgileridir (genellikle API anahtarı veya kullanıcı adı-şifre). Bunları bir kere kaydedersiniz, n8n güvenli bir şekilde saklar ve istediğiniz workflow'larda tekrar tekrar kullanabilirsiniz.

**Expression (İfade):** Bir node'un içine, sabit bir değer yerine "dinamik" (değişken) bir değer yazmanızı sağlayan özel formül sistemidir. Örneğin `{{ $json.email }}` ifadesi, önceki node'dan gelen verinin içindeki "email" alanını otomatik olarak alır.

**JSON:** Verinin bilgisayarlar arasında taşınmasında kullanılan, okunması kolay bir format. Şuna benzer:
```json
{
  "isim": "Ahmet",
  "yas": 28,
  "sehir": "İzmir"
}
```
n8n'de tüm veriler bu formatta akar. Korkmayın, ileride detaylı örneklerle göreceğiz.

**Canvas (Tuval):** n8n'in ana çalışma alanıdır — node'ları sürükleyip bıraktığınız, bağlantıları çizdiğiniz büyük beyaz/gri alan.

---

## Bölüm 3: n8n'i Kurmak — Tüm Yöntemler

n8n'i kullanmaya başlamak için birkaç farklı yol var. Hangisinin sizin için uygun olduğunu birlikte değerlendirelim.

### 3.1 Yöntem 1: n8n Cloud (En Kolay Yol)

Eğer hiçbir teknik kurulumla uğraşmak istemiyorsanız, n8n'in resmi web sitesinden (n8n.io) bir hesap oluşturarak bulut sürümünü kullanabilirsiniz. Bu yöntemde:

- Hiçbir şey kurmanıza gerek yok
- Tarayıcınızdan doğrudan erişebilirsiniz
- Ücretsiz deneme süresi sunulur, sonrasında aylık ücret alınır
- Kurulum, bakım, güncelleme gibi işlerle hiç ilgilenmezsiniz

**Kimler için uygun?** Hızlıca başlamak isteyen, sunucu yönetimiyle hiç ilgilenmek istemeyen, bütçesi olan kullanıcılar için idealdir.

**Adımlar:**
1. Tarayıcınızdan **n8n.io** adresine gidin.
2. Sağ üstteki "Get started" veya "Sign up" butonuna tıklayın.
3. E-posta adresinizle veya Google hesabınızla kayıt olun.
4. E-postanıza gelen doğrulama linkine tıklayın.
5. Karşınıza n8n'in ana ekranı (canvas) gelecek — tebrikler, artık otomasyon kurmaya hazırsınız!

### 3.2 Yöntem 2: Kendi Bilgisayarınızda Çalıştırmak (Self-Hosted - Docker ile)

Eğer verilerinizin tamamen kendi kontrolünüzde olmasını istiyorsanız, ücretsiz ve sınırsız kullanmak istiyorsanız, **kendi bilgisayarınızda** veya **kendi sunucunuzda** n8n'i çalıştırabilirsiniz. Bu yöntem biraz teknik gibi görünebilir ama adım adım takip ettiğinizde oldukça kolaydır.

Bunun için **Docker** adlı bir programa ihtiyacımız var. Docker, bir uygulamayı "kutu" (container) içine koyup, bilgisayarınızın işletim sisteminden bağımsız olarak çalıştırmanızı sağlayan bir araçtır. Bunu şöyle düşünebilirsiniz: Docker, n8n'i çalıştırmak için gereken her şeyi (programlama dili, ayarlar, kütüphaneler) hazır bir "paket" halinde size sunar, siz de bu paketi bilgisayarınızda çalıştırırsınız.

**Adım 1: Docker'ı İndirin ve Kurun**

1. Tarayıcınızdan **docker.com** adresine gidin.
2. "Docker Desktop" butonuna tıklayın ve işletim sisteminize uygun sürümü (Windows, Mac veya Linux) indirin.
3. İndirilen kurulum dosyasını çalıştırın ve ekrandaki talimatları takip ederek kurulumu tamamlayın.
4. Kurulum bittiğinde bilgisayarınızı yeniden başlatmanız gerekebilir.
5. Yeniden başlattıktan sonra Docker Desktop uygulamasını açın. Sol altta veya üstte bir "balina" simgesi göreceksiniz — bu Docker'ın çalıştığını gösterir.

**Adım 2: Komut Satırını (Terminal) Açın**

- **Windows kullanıcıları**: Başlat menüsüne "PowerShell" yazın ve açın.
- **Mac kullanıcıları**: Spotlight'a (Cmd+Boşluk) "Terminal" yazın ve açın.
- **Linux kullanıcıları**: Terminal uygulamanızı açın (genellikle Ctrl+Alt+T).

Korkmayın, "komut satırı" sadece yazı yazarak bilgisayarınıza komut verdiğiniz siyah (veya beyaz) bir penceredir. Aşağıdaki komutu kopyalayıp bu pencereye yapıştırıp Enter tuşuna basacağız.

**Adım 3: n8n'i Başlatan Komutu Çalıştırın**

Aşağıdaki komutu terminale yapıştırın ve Enter'a basın:

```bash
docker volume create n8n_data

docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```

Bu komut ne yapıyor, açıklayalım:

- `docker volume create n8n_data`: n8n'in verilerinizi (workflowlarınızı, ayarlarınızı) saklayacağı bir "depo" oluşturur. Bu sayede bilgisayarınızı kapatıp açtığınızda verileriniz kaybolmaz.
- `docker run`: Docker'a "şu uygulamayı çalıştır" diyoruz.
- `-p 5678:5678`: n8n'e tarayıcınızdan ulaşabilmeniz için 5678 numaralı "kapı" (port) açıyoruz.
- `-v n8n_data:/home/node/.n8n`: Az önce oluşturduğumuz depoyu n8n'e bağlıyoruz.
- `docker.n8n.io/n8nio/n8n`: Çalıştırılacak programın adı — yani n8n'in kendisi.

İlk çalıştırmada bilgisayarınız n8n programını internetten indirecek, bu birkaç dakika sürebilir. İndirme bittiğinde terminalde şuna benzer bir yazı göreceksiniz:

```
Editor is now accessible via:
http://localhost:5678/
```

**Adım 4: n8n'e Tarayıcıdan Erişin**

Tarayıcınızı açın (Chrome, Edge, Firefox - hangisi olursa) ve adres çubuğuna şunu yazın:

```
http://localhost:5678
```

Karşınıza n8n'in kurulum ekranı gelecek. Burada bir e-posta adresi, ad-soyad ve şifre belirleyerek kendi yerel hesabınızı oluşturacaksınız. Bu bilgiler sadece sizin bilgisayarınızda saklanır, hiçbir yere gönderilmez.

**Önemli not:** Terminal penceresini kapatırsanız n8n de durur. n8n'i sürekli arka planda çalıştırmak için "detached mode" denilen bir yöntem kullanabiliriz — bunu ileri seviye bölümde göreceğiz.

### 3.3 Yöntem 3: Sunucuda (VPS) Kalıcı Kurulum

Eğer n8n'inizin 7/24 çalışmasını, bilgisayarınızı kapattığınızda da otomasyonlarınızın devam etmesini istiyorsanız, bir **VPS (Virtual Private Server - Sanal Özel Sunucu)** kiralamanız gerekir. Bu, internet üzerinden kiraladığınız, 7/24 açık olan uzak bir bilgisayardır.

Popüler VPS sağlayıcıları: DigitalOcean, Hetzner, Contabo, AWS, Google Cloud.

Bu rehberin kapsamı dışında detaylı sunucu kurulumuna girmeyeceğiz, ama temel mantık şu şekilde:

1. Bir VPS satın alırsınız (aylık genellikle 5-10 dolar civarı bir Ubuntu sunucu yeterlidir)
2. SSH (uzak bağlantı) ile sunucunuza bağlanırsınız
3. Docker'ı sunucuya kurarsınız
4. Yukarıdaki Docker komutunu sunucuda çalıştırırsınız, ancak `--restart always` parametresini eklersiniz ki sunucu yeniden başladığında n8n de otomatik başlasın
5. İsteğe bağlı olarak bir alan adı (domain) bağlayıp, HTTPS (güvenli bağlantı) ekleyebilirsiniz

Eğer ileride bu konuda detaylı bir rehbere ihtiyacınız olursa, bu konuyu ayrı bir makale olarak da hazırlayabiliriz.

### 3.4 Hangi Yöntemi Seçmeliyim?

- **Sadece deneme yapmak, n8n'i öğrenmek istiyorsanız** → n8n Cloud'un ücretsiz deneme sürümü veya kendi bilgisayarınızda Docker.
- **Kişisel projeleriniz için, internet bağlantınız 7/24 açık değilse ama maliyet önemliyse** → Kendi bilgisayarınızda Docker, ihtiyaç oldukça açıp kapatarak.
- **İşletmeniz için, otomasyonların sürekli ve kesintisiz çalışması gerekiyorsa** → VPS üzerinde kalıcı kurulum veya n8n Cloud'un ücretli planı.

---

## Bölüm 4: n8n Arayüzünü Tanıyalım

n8n'i açtığınızda karşınıza gelen ekranı parça parça inceleyelim. Bu, evinizin odalarını tanımak gibi — bir kere nerede ne olduğunu öğrendiğinizde, içinde kaybolmazsınız.

### 4.1 Ana Ekran (Overview / Workflows Sayfası)

n8n'e giriş yaptığınızda karşınıza çıkan ilk sayfa, oluşturduğunuz tüm workflow'ların listesidir. Burada şunları görürsünüz:

- Sol tarafta bir menü: "Overview" (Genel Bakış), "Personal" (Kişisel), "Credentials" (Kimlik Bilgileri), "Executions" (Çalıştırma Geçmişi), "Templates" (Hazır Şablonlar)
- Sağ üstte "+ Add workflow" veya "Create Workflow" butonu — yeni bir otomasyon oluşturmak için
- Ortada, daha önce oluşturduğunuz workflow'ların kartları (eğer henüz hiç oluşturmadıysanız burası boş olacak)

### 4.2 Workflow Düzenleme Ekranı (Canvas)

"Create Workflow" butonuna tıkladığınızda, sizi büyük, boş, gri/beyaz bir alana yönlendirir. Burası **canvas** dediğimiz, otomasyonunuzu görsel olarak inşa edeceğiniz alandır.

Bu ekranda dikkat etmeniz gereken bölümler:

**Üst orta - Workflow Adı:** Workflow'unuza isim verebileceğiniz alan. Buraya "İsimsiz İş Akışı" yazıyor, tıklayıp değiştirebilirsiniz. Örneğin "Sabah Hava Durumu Bildirimi" gibi anlamlı bir isim verin.

**Üst sağ - Save (Kaydet) Butonu:** Yaptığınız değişiklikleri kaydeder. n8n bazen otomatik kaydeder ama elle kaydetmek her zaman güvenlidir.

**Üst sağ - Active/Inactive Anahtarı (Toggle):** Bu, workflow'unuzun "açık" mı "kapalı" mı olduğunu gösteren bir düğmedir. Workflow'unuz tamamlandığında ve test ettiğinizde, bu düğmeyi "aktif" konuma getirirsiniz ve otomasyon gerçek zamanlı çalışmaya başlar.

**Sol orta - "+" (Artı) Butonu veya Boş Canvas:** Boş bir workflow açtığınızda ortada büyük bir "+" işareti veya "Add first step" (İlk adımı ekle) yazısı görürsünüz. Buraya tıklayarak ilk node'unuzu (genellikle bir tetikleyici) ekleyebilirsiniz.

**Alt kısım - Çalıştırma Sonuçları Paneli:** Bir workflow'u test ettiğinizde, alt tarafta her node'un ne kadar veri işlediğini, hata olup olmadığını gösteren bir panel açılır.

### 4.3 Node Ekleme Paneli

Canvas üzerinde "+" butonuna tıkladığınızda veya canvas'a çift tıkladığınızda, sağdan bir panel açılır. Bu panelde:

- Üstte bir **arama kutusu** vardır — "Gmail", "Telegram", "Google Sheets" gibi yazarak istediğiniz uygulamayı arayabilirsiniz.
- Altta kategoriler halinde gruplanmış node'lar listelenir: "Trigger" (Tetikleyiciler), "App" (Uygulamalar), "Core Nodes" (Temel Düğümler - veri işleme, koşullar vb.), "AI" (Yapay Zeka düğümleri) gibi.

İlk node'unuzu eklemek için bu panelden ne istediğiniz node'a tıklamanız yeterli.

### 4.4 Bir Node'un İçini Açmak

Canvas üzerindeki bir node'a çift tıkladığınızda (veya tek tıklayıp ortaya çıkan kalem ikonuna basarak), o node'un **ayar paneli** açılır. Bu panel genellikle ekranın sağ yarısını kaplar ve şu bölümlerden oluşur:

- **Sol taraf:** Bu node'un alacağı "girdi" (input) verisi — yani önceki node'dan gelen veri burada görünür.
- **Orta:** Node'un kendi ayarları — örneğin bir Gmail node'u için "Kime gönderilecek", "Konu", "Mesaj İçeriği" gibi alanlar.
- **Sağ taraf:** Bu node çalıştığında üreteceği "çıktı" (output) verisinin önizlemesi.

Bu üçlü görünüm, n8n'in en güçlü özelliklerinden biridir çünkü **verinin her node'dan sonra nasıl değiştiğini görsel olarak takip edebilirsiniz.**

---

## Bölüm 5: İlk Otomasyonunuzu Oluşturalım — "Merhaba Dünya"

Teorik bilgiyi bir kenara koyup şimdi gerçekten ellerimizi kirletelim. İlk otomasyonumuz çok basit olacak: butona bastığınızda size bir mesaj gösteren bir workflow.

### 5.1 Adım Adım: İlk Workflow

**Adım 1:** n8n ana ekranında sağ üstteki "Create Workflow" butonuna tıklayın. Karşınıza boş bir canvas gelecek.

**Adım 2:** Canvas'ın ortasındaki "Add first step" yazısına tıklayın (veya "+" butonuna).

**Adım 3:** Açılan panelde arama kutusuna "Manual" yazın. Karşınıza **"Trigger manually"** (Manuel olarak tetikle) seçeneği çıkacak. Bu, "Test" butonuna her bastığınızda workflow'un çalışmasını sağlayan en basit tetikleyicidir. Bu seçeneğe tıklayın.

Şimdi canvas'ınızda "When clicking 'Test workflow'" yazılı bir kutucuk (node) belirecek.

**Adım 4:** Bu node'un sağındaki küçük "+" işaretine tıklayarak ikinci bir node ekleyelim. Arama kutusuna "Edit Fields" yazın ve **"Edit Fields (Set)"** node'unu seçin. Bu node, yeni bir veri oluşturmamızı sağlar.

**Adım 5:** Açılan ayar panelinde "Add Field" (Alan Ekle) butonuna tıklayın. Şu bilgileri girin:
- **Name (İsim):** `mesaj`
- **Type (Tür):** String (Metin)
- **Value (Değer):** `Merhaba! İlk n8n otomasyonumu başarıyla kurdum.`

**Adım 6:** Şimdi sağ üstteki "Test workflow" (veya canvas ortasındaki "Test" butonuna) tıklayın. n8n her iki node'u sırayla çalıştıracak ve her node'un üzerinde küçük yeşil bir tik işareti göreceksiniz — bu, o node'un başarıyla çalıştığını gösterir.

**Adım 7:** "Edit Fields" node'una tıklayarak çıktısını kontrol edin. Sağ tarafta şuna benzer bir JSON göreceksiniz:

```json
{
  "mesaj": "Merhaba! İlk n8n otomasyonumu başarıyla kurdum."
}
```

Tebrikler! İlk otomasyonunuzu oluşturdunuz. Şimdi henüz "gerçek dünyada" bir işe yaramıyor ama burada öğrendiğiniz şey çok önemli: **node'ları birbirine bağlamak, veri oluşturmak ve test etmek.**

### 5.2 JSON'a Daha Yakından Bakalım

n8n'de her node'un girdisi ve çıktısı JSON formatındadır. JSON, verileri "anahtar: değer" (key: value) çiftleri halinde saklayan bir formattır. Bunu bir form gibi düşünebilirsiniz:

```json
{
  "ad": "Ayşe",
  "soyad": "Yılmaz",
  "email": "ayse@example.com",
  "yas": 32,
  "aktif": true,
  "hobiler": ["okuma", "yüzme", "fotoğrafçılık"]
}
```

Burada:
- `"ad": "Ayşe"` — "ad" anahtarının değeri "Ayşe" metnidir.
- `"yas": 32` — "yas" anahtarının değeri 32 sayısıdır (tırnak içinde değil, çünkü sayı).
- `"aktif": true` — "aktif" anahtarının değeri "true" (doğru/evet) — bu "boolean" denilen evet/hayır tipi bir değerdir.
- `"hobiler": [...]` — "hobiler" anahtarının değeri bir liste (array)'dir, içinde birden fazla metin var.

n8n'de bir node'dan gelen veriye ulaşmak için `{{ $json.ad }}` gibi ifadeler kullanırız — bu, "önceki node'dan gelen JSON verisinin 'ad' alanını al" demektir. İleride bunu çok kullanacağız.

---

## Bölüm 6: Tetikleyiciler (Triggers) — Otomasyonunuz Nasıl Başlar?

Bir otomasyonun en kritik kısmı, "ne zaman" çalışacağını belirleyen tetikleyicidir. n8n'de birçok farklı tetikleyici türü vardır. En önemlilerini inceleyelim.

### 6.1 Manual Trigger (Manuel Tetikleyici)

Az önce kullandığımız tetikleyicidir. Sadece test amaçlı kullanılır — "Test workflow" butonuna bastığınızda çalışır. Gerçek/canlı otomasyonlarda kullanılmaz, sadece geliştirme aşamasında işinizi görür.

### 6.2 Schedule Trigger (Zamanlama Tetikleyicisi)

Bu, en sık kullanılan tetikleyicilerden biridir. Belirlediğiniz zaman aralıklarında otomatik olarak çalışır. Örnekler:

- Her gün sabah 08:00'de
- Her saat başı
- Her hafta Pazartesi günü
- Her ayın 1'inde
- Her 15 dakikada bir

Bu tetikleyiciyi eklediğinizde, ayar panelinde "Trigger Interval" (Tetikleme Aralığı) seçeneği çıkar. Buradan "Days" (Günler), "Hours" (Saatler), "Minutes" (Dakikalar), "Cron Expression" (özel zamanlama formülü) gibi seçenekler arasından istediğinizi seçebilirsiniz.

**Örnek kullanım:** "Her sabah 07:30'da hava durumunu kontrol et ve eğer yağmur yağacaksa Telegram'dan bana mesaj gönder."

### 6.3 Webhook Trigger (Web Kancası Tetikleyicisi)

Bu, n8n'in en güçlü özelliklerinden biridir ve biraz daha teknik bir kavram, ama açıklayınca çok anlaşılır olacak.

**Webhook ne demek?** "Web" (internet) + "Hook" (kanca/çengel). Webhook, bir uygulamanın "bir şey olduğunda bana haber ver" diyerek başka bir sisteme verdiği bir **internet adresi (link)**dir.

Düşünün ki n8n'de bir webhook node'u oluşturuyorsunuz. n8n size şöyle bir link üretiyor:

```
https://sizin-n8n-adresiniz.com/webhook/abc123
```

Şimdi bu linki başka bir sisteme (örneğin web sitenizin iletişim formuna, bir ödeme sistemine, bir mobil uygulamaya) verirseniz, o sistem "bir şey olduğunda" (örneğin form doldurulduğunda) bu linke otomatik olarak veri gönderir. n8n bu veriyi alır ve workflow'unuzu başlatır.

**Gerçek hayat örneği:** Web sitenizde bir "Bize Ulaşın" formu var. Bu formu n8n'in webhook linkine bağlarsanız, form her doldurulduğunda:
1. n8n bu veriyi (kişinin adı, e-postası, mesajı) alır
2. Otomatik olarak bir Google Sheets'e satır olarak ekler
3. Size Telegram'dan "Yeni bir mesaj geldi!" bildirimi gönderir
4. Kişiye otomatik bir "Mesajınızı aldık, en kısa sürede dönüş yapacağız" e-postası gönderir

Tüm bunlar, **siz hiçbir şey yapmadan**, form doldurulduğu anda otomatik gerçekleşir.

### 6.4 App Trigger'ları (Uygulama Tetikleyicileri)

Bazı uygulamaların kendine özel tetikleyicileri vardır. Örneğin:

- **Gmail Trigger:** Yeni bir e-posta geldiğinde tetiklenir.
- **Telegram Trigger:** Telegram botunuza bir mesaj geldiğinde tetiklenir.
- **Google Sheets Trigger:** Bir tabloya yeni satır eklendiğinde tetiklenir.
- **Slack Trigger:** Bir Slack kanalına mesaj atıldığında tetiklenir.

Bu tetikleyiciler, ilgili uygulamanın hesabınıza bağlanmasını gerektirir (buna "credential" - kimlik bilgisi diyoruz, az sonra detaylı göreceğiz).

---

## Bölüm 7: Kimlik Bilgileri (Credentials) — n8n'i Diğer Uygulamalara Bağlamak

n8n'in başka bir uygulamayla (Gmail, Telegram, Google Sheets vb.) çalışabilmesi için, o uygulamaya "giriş yapması" gerekir. Buna **credential (kimlik bilgisi)** diyoruz.

### 7.1 Credential Nedir, Nasıl Çalışır?

Düşünün ki bir arkadaşınızdan "benim adıma Gmail'imi kontrol eder misin?" diye bir rica geldi. Bunu yapabilmesi için arkadaşınızın sizin Gmail şifrenizi bilmesi gerekir, değil mi? n8n için de mantık benzer, ama daha güvenli bir şekilde işliyor.

Çoğu modern uygulama, şifrenizi doğrudan paylaşmak yerine **API anahtarı (API Key)** veya **OAuth** denilen bir güvenli giriş yöntemi sunar.

- **API Key:** Uzun, rastgele bir kod dizisidir (örneğin: `sk-a1b2c3d4e5f6...`). Bu kodu n8n'e verdiğinizde, n8n bu kodu kullanarak o servise "ben yetkiliyim" diyerek erişim sağlar.

- **OAuth:** Daha kullanıcı dostu bir yöntemdir. n8n sizi ilgili servisin (örneğin Google'ın) giriş sayfasına yönlendirir, siz orada normal şekilde giriş yaparsınız ve "n8n'e izin ver" derseniz, n8n arkaplanda güvenli bir şekilde erişim kazanır. Şifrenizi n8n hiçbir zaman görmez.

### 7.2 Bir Credential Nasıl Oluşturulur?

Genel adımlar şu şekildedir (uygulamadan uygulamaya küçük farklar olabilir):

1. Sol menüden **"Credentials"** sekmesine gidin.
2. Sağ üstteki **"Add Credential"** butonuna tıklayın.
3. Bağlanmak istediğiniz uygulamayı arayın (örneğin "Telegram").
4. Açılan formda istenen bilgileri girin (API anahtarı, kullanıcı adı, OAuth girişi vb.)
5. **"Save"** (Kaydet) butonuna tıklayın.

Artık bu credential, ilgili uygulamanın node'larını eklediğinizde otomatik olarak seçenek listesinde görünecek ve seçebileceksiniz.

### 7.3 Örnek: Telegram Bot Credential'ı Oluşturmak

Telegram, n8n öğrenmeye başlayanlar için en kolay ve en eğlenceli entegrasyonlardan biridir, çünkü ücretsizdir ve kurulumu çok hızlıdır. Adım adım gidelim:

**Adım 1: Telegram'da Bot Oluşturun**

1. Telefonunuzda veya bilgisayarınızda Telegram uygulamasını açın.
2. Arama kutusuna **"BotFather"** yazın ve resmi BotFather hesabını bulun (mavi tik işaretli olmalı).
3. BotFather ile sohbet başlatın ve `/newbot` komutunu yazın.
4. Bot'unuza bir isim verin (örneğin "Toprak Otomasyon Botu").
5. Bot'unuza benzersiz bir kullanıcı adı verin (sonu "bot" ile bitmeli, örneğin "toprak_otomasyon_bot").
6. BotFather size uzun bir **token** (anahtar) verecek, şuna benzer:
```
123456789:ABCdefGHIjklMNOpqrSTUvwxYZ1234567890
```
Bu kodu kopyalayın ve güvenli bir yere kaydedin — bu sizin bot'unuzun "şifresidir".

**Adım 2: n8n'de Telegram Credential'ı Ekleyin**

1. n8n'de "Credentials" → "Add Credential" → "Telegram" arayın.
2. Açılan kutuya, BotFather'dan aldığınız token'ı yapıştırın.
3. "Save" butonuna tıklayın.

**Adım 3: Bot'unuza Mesaj Gönderin (İlk Tetikleme)**

Telegram'da bot'unuzu arayın ve ona herhangi bir mesaj gönderin (örneğin "Merhaba"). Bu önemli, çünkü bot, sizinle önce siz konuşmadıysanız size mesaj gönderemez.

**Adım 4: Test Edin**

n8n'de yeni bir workflow oluşturun:
1. "Manual Trigger" node'u ekleyin.
2. Yanına "Telegram" node'u ekleyin, "Send a text message" işlemini seçin.
3. Az önce oluşturduğunuz credential'ı seçin.
4. "Chat ID" alanına kendi Telegram kullanıcı ID'nizi yazmanız gerekiyor (bunu öğrenmek için Telegram'da "@userinfobot" adlı bota mesaj atabilirsiniz, size ID'nizi verecektir).
5. "Text" alanına bir mesaj yazın, örneğin: "n8n'den merhaba!"
6. "Test workflow" butonuna basın.

Telegram'ı kontrol edin — bot'unuzdan mesajı almış olmalısınız! Bu, n8n'in dış dünyaya ilk "konuştuğu" andır ve gerçekten heyecan verici bir adımdır.

---

## Bölüm 8: Temel Node Türleri — Verinizi İşlemek

Şimdi n8n'in "beyni" olan, veriyi işleyen, dönüştüren, filtreleyen, karar veren temel node'ları öğrenelim. Bunlar her otomasyonun bel kemiğidir.

### 8.1 Edit Fields (Set) — Veri Oluşturma ve Düzenleme

Bu node, daha önce kullandığımız node'dur. Yeni veri oluşturmak veya mevcut veriyi değiştirmek için kullanılır. İki modu vardır:

- **Manual Mapping:** Alanları tek tek elle eklersiniz (isim, tür, değer).
- **JSON:** Doğrudan JSON formatında veri yazarsınız.

**Örnek kullanım:** Bir webhook'tan gelen karmaşık veriyi, sadece ihtiyacınız olan alanları seçerek sadeleştirmek.

### 8.2 IF Node — Koşullu Dallanma

"IF" İngilizce "eğer" demektir. Bu node, gelen veriye göre workflow'u **iki farklı yola** ayırmanızı sağlar: "Doğru" (True) ve "Yanlış" (False).

**Nasıl çalışır?** IF node'una bir koşul tanımlarsınız, örneğin "Eğer gelen e-postanın konusu 'Fatura' kelimesini içeriyorsa". Eğer bu koşul doğruysa, veri "True" çıkışından devam eder; yanlışsa "False" çıkışından devam eder. Her iki çıkışa da farklı node'lar bağlayarak, farklı senaryolar için farklı işlemler yapabilirsiniz.

**Gerçek hayat örneği:**
```
E-posta Geldi
    ↓
IF: Konu "Fatura" içeriyor mu?
    ↓ (True)                    ↓ (False)
Muhasebe klasörüne taşı    Genel klasöre taşı
```

### 8.3 Switch Node — Çoklu Dallanma

IF node sadece iki seçenek sunarken, **Switch** node birden fazla seçenek sunar. Örneğin bir müşteri talebinin "Teknik Destek", "Satış", "Şikayet" veya "Diğer" olarak sınıflandırılması ve her birinin farklı bir ekibe yönlendirilmesi gibi durumlarda kullanılır.

```
Müşteri Mesajı Geldi
    ↓
Switch: Mesaj kategorisi nedir?
    ├── "Teknik Destek" → Teknik ekibe Slack mesajı
    ├── "Satış" → Satış ekibine e-posta
    ├── "Şikayet" → Yöneticiye acil bildirim
    └── "Diğer" → Genel kutuya kaydet
```

### 8.4 Loop Over Items (Split in Batches) — Tekrarlayan İşlemler

Bazen tek bir node çıktısında **birden fazla öğe (item)** olur. Örneğin bir Google Sheets'ten 50 satır okuduğunuzda, bunların her biri ayrı bir "item"dır. Eğer her bir satır için ayrı ayrı bir işlem yapmak istiyorsanız (örneğin her birine ayrı bir e-posta göndermek), **Loop Over Items** node'unu kullanırsınız.

Bu node, gelen veriyi küçük gruplara (batch) bölerek, her grubu sırayla işler. Bu, hem performans açısından hem de bazı uygulamaların "aynı anda çok fazla istek" sınırlamalarına uymak açısından önemlidir.

### 8.5 Merge Node — Verileri Birleştirme

Bazı durumlarda iki farklı kaynaktan gelen veriyi birleştirmeniz gerekir. Örneğin bir Google Sheets'ten müşteri listesini, başka bir kaynaktan da bu müşterilerin sipariş bilgilerini çekip, ikisini birleştirip tek bir tabloda göstermek isteyebilirsiniz. **Merge** node bu işi yapar — farklı yöntemlerle (alt alta ekleme, eşleştirerek birleştirme vb.) iki veri akışını birleştirir.

### 8.6 Code Node — Kod Yazarak Sınırsız Özelleştirme

Eğer hazır node'lar ihtiyacınızı karşılamıyorsa, **Code** node'unu kullanarak JavaScript (veya Python) kodu yazabilirsiniz. Bu, n8n'in "ileri seviye kapısı"dır. Kod bilmeyen kullanıcılar için bu node biraz ürkütücü olabilir, ama temel n8n kullanımında bu node'a ihtiyacınız çoğu zaman olmaz — hazır node'lar genellikle yeterlidir.

**Basit bir örnek (isteğe bağlı, ileri seviye):**
```javascript
// Gelen tüm itemların "yas" değerini 1 artır
for (const item of $input.all()) {
  item.json.yas = item.json.yas + 1;
}
return $input.all();
```

### 8.7 HTTP Request Node — Her Şeye Bağlanma Kapısı

n8n'de hazır node'u olmayan bir uygulamaya/servise bağlanmanız gerekiyorsa, **HTTP Request** node'unu kullanırsınız. Bu node, internetteki herhangi bir "API"ye istek gönderebilen evrensel bir araçtır.

**API nedir?** API (Application Programming Interface), bir uygulamanın "ben sana şu bilgileri verebilirim, sen de bana şu komutları gönderebilirsin" diyerek sunduğu bir kapıdır. Örneğin bir hava durumu sitesinin API'sine "İzmir'in bugünkü hava durumu nedir?" diye sorduğunuzda, size JSON formatında bir cevap döner: `{"sicaklik": 28, "durum": "güneşli"}`.

n8n'de 400'den fazla hazır entegrasyon olsa da, dünyada milyonlarca API var. HTTP Request node, n8n'in desteklemediği herhangi bir servise bile bağlanmanızı sağlar — yeterli ki o servisin bir API'si olsun ve nasıl kullanılacağını (API dokümantasyonunu) bulun.

---

## Bölüm 9: İfadeler (Expressions) — n8n'in Gizli Süper Gücü

n8n'i gerçekten güçlü kılan şey, node'lar arasında **veri akışını dinamik olarak kontrol edebilmenizdir**. Bunu sağlayan araç, **expression (ifade)** sistemidir.

### 9.1 İfade Nedir?

Normalde bir node'un içine sabit (statik) bir değer yazarsınız, örneğin Telegram mesajı için "Merhaba!" yazarsınız. Ama bazen bu değerin **önceki node'dan gelen veriye göre değişmesini** istersiniz. Örneğin:

"Merhaba [İsim], siparişiniz [Sipariş No] alındı."

Burada `[İsim]` ve `[Sipariş No]` her kullanıcı için farklı olmalı. İşte bunu n8n'de şu şekilde yazarız:

```
Merhaba {{ $json.isim }}, siparişiniz {{ $json.siparisNo }} alındı.
```

`{{ }}` çift süslü parantezler arasına yazılan her şey, n8n tarafından "hesaplanır" ve gerçek değerle değiştirilir. Bu sistemin adı **expression**'dır.

### 9.2 En Sık Kullanılan İfadeler

**`$json`** — Şu anki node'a gelen verinin tamamına erişmenizi sağlar.
```
{{ $json.email }}
```
Bu, gelen verideki "email" alanının değerini getirir.

**`$node["Node Adı"].json`** — Belirli bir node'dan (sadece hemen önceki değil, herhangi birinden) veri çekmenizi sağlar.
```
{{ $node["Webhook"].json.isim }}
```
Bu, "Webhook" adlı node'dan gelen verideki "isim" alanını getirir.

**`$now`** — Şu anki tarih ve saati getirir.
```
{{ $now }}
```

**`$today`** — Bugünün tarihini getirir (saat olmadan).

**Matematiksel işlemler:**
```
{{ $json.fiyat * 1.20 }}
```
Bu, "fiyat" değerini %20 artırır (örneğin KDV hesaplaması için).

**Metin birleştirme:**
```
{{ $json.ad + " " + $json.soyad }}
```
Bu, ad ve soyadı bir boşlukla birleştirir.

**Koşullu ifadeler (ternary):**
```
{{ $json.yas >= 18 ? "Yetişkin" : "Çocuk" }}
```
Bu, yaş 18 veya üzeriyse "Yetişkin", değilse "Çocuk" yazar.

### 9.3 İfadeleri Nerede Kullanırım?

n8n'de neredeyse her metin alanının yanında küçük bir simge (genellikle bir "fx" veya zar/dadu simgesi) görürsünüz. Bu simgeye tıkladığınızda, o alan "expression modu"na geçer ve `{{ }}` ile yazabileceğiniz hale gelir. n8n aynı zamanda, ifadenizi yazarken **canlı önizleme** gösterir — yani gerçek veriyle ne çıkacağını yazarken görebilirsiniz. Bu, hata yapma riskini büyük ölçüde azaltır.

---

## Bölüm 10: Gerçek Bir Otomasyon Projesi — Adım Adım

Şimdi öğrendiklerimizi birleştirip, **gerçekten kullanışlı** bir otomasyon kuralım: **"Web sitesi formu doldurulduğunda, bilgileri Google Sheets'e kaydet ve Telegram'dan bana bildirim gönder."**

Bu, küçük işletmeler, freelancerlar ve içerik üreticileri için son derece kullanışlı bir otomasyondur.

### 10.1 Senaryo

Diyelim ki bir web siteniz var ve "Bize Ulaşın" formunuz var. Form alanları: Ad, E-posta, Mesaj. Bu form doldurulduğunda:

1. Bilgiler bir Google Sheets dosyasına satır olarak eklensin.
2. Size Telegram'dan "Yeni bir mesaj var!" bildirimi gelsin.
3. Formu dolduran kişiye otomatik bir "Teşekkürler" e-postası gönderilsin.

### 10.2 Adım Adım Kurulum

**Adım 1: Webhook Node'unu Ekleyin**

1. Yeni bir workflow oluşturun, adını "İletişim Formu Otomasyonu" yapın.
2. İlk node olarak "Webhook" arayın ve ekleyin.
3. Ayarlarda "HTTP Method" olarak **POST** seçin (formlar genellikle POST ile veri gönderir).
4. n8n size bir "Test URL" ve bir "Production URL" verecek. Test URL'yi şimdilik kopyalayın.

**Önemli not:** Gerçek bir web sitesi formunu bu webhook'a bağlamak, sitenizin formunun "action" adresini bu webhook URL'si yapmayı gerektirir. Bu, sitenizin yapısına bağlı olarak değişir (WordPress, özel kodla yazılmış site, Webflow vb. farklı yöntemler gerektirir). Bu rehberde, formdan **gelecek veriyi simüle ederek** öğrenmeye odaklanacağız; gerçek formunuzu bağlama konusunda kullandığınız platforma özel rehberlere bakmanız gerekebilir.

**Adım 2: Test Verisi ile Çalıştırma**

Webhook node'una çift tıklayın ve "Listen for Test Event" butonuna basın. n8n şimdi "bekleme" moduna geçer ve o webhook URL'sine bir veri gelmesini bekler.

Başka bir programdan (örneğin tarayıcınızda açtığınız basit bir araç veya bilgisayarınızdaki terminal) şu şekilde test verisi gönderebilirsiniz, ama basitlik için n8n'in kendi "Test" özelliğini kullanmak da yeterlidir — node'a tıkladığınızda örnek bir JSON yapısı oluşturup devam edebilirsiniz.

Şimdilik, manuel olarak bir "Edit Fields" node'u ile şu örnek veriyi oluşturalım (gerçek formdan geliyormuş gibi):

```json
{
  "ad": "Mehmet Demir",
  "email": "mehmet@example.com",
  "mesaj": "Merhaba, hizmetleriniz hakkında bilgi almak istiyorum."
}
```

**Adım 3: Google Sheets'e Bağlanın**

1. Önce Google Sheets'te yeni bir dosya oluşturun. İlk satıra şu başlıkları yazın: `Ad`, `Email`, `Mesaj`, `Tarih`.
2. n8n'de yeni bir node ekleyin: "Google Sheets" arayın.
3. İşlem (Operation) olarak "Append Row" (Satır Ekle) seçin.
4. Credential oluşturmanız istenecek — Google hesabınızla giriş yapıp izin verin (OAuth yöntemi).
5. Açılır listeden, az önce oluşturduğunuz Google Sheets dosyasını ve sayfasını (sheet) seçin.
6. Her sütun için hangi veriyi yazacağını eşleştirin:
   - `Ad` sütunu → `{{ $json.ad }}`
   - `Email` sütunu → `{{ $json.email }}`
   - `Mesaj` sütunu → `{{ $json.mesaj }}`
   - `Tarih` sütunu → `{{ $now }}`

**Adım 4: Telegram Bildirimi Ekleyin**

Bölüm 7'de oluşturduğumuz Telegram credential'ını kullanarak:

1. Yeni bir node ekleyin: "Telegram" → "Send a text message".
2. "Chat ID" alanına kendi Telegram ID'nizi yazın.
3. "Text" alanına şu ifadeyi yazın:

```
🔔 Yeni bir iletişim formu mesajı!

Ad: {{ $json.ad }}
E-posta: {{ $json.email }}
Mesaj: {{ $json.mesaj }}
```

**Adım 5: Otomatik Teşekkür E-postası Ekleyin**

1. Yeni bir node ekleyin: "Gmail" veya "Send Email" (SMTP) → "Send a message".
2. Eğer Gmail kullanıyorsanız, Google hesabınızla OAuth ile bağlanın.
3. "To" alanına: `{{ $json.email }}`
4. "Subject" alanına: `Mesajınızı Aldık!`
5. "Message" alanına:

```
Merhaba {{ $json.ad }},

Mesajınızı aldık, en kısa sürede size geri dönüş yapacağız.

Teşekkürler,
Siber Akademi Ekibi
```

**Adım 6: Workflow'u Aktif Edin**

Sağ üstteki "Active" düğmesini açın. Artık workflow'unuz, gerçek formunuz bu webhook'a bağlandığı anda **7/24 otomatik çalışmaya başlayacak.**

### 10.3 Bu Otomasyonun Mantığını Çözelim

Bu örnek üzerinden, herhangi bir otomasyonu tasarlarken sorulması gereken temel soruları öğrenelim:

1. **Tetikleyici ne olacak?** (Bu örnekte: Webhook — form doldurulduğunda)
2. **Hangi veriler geliyor?** (Ad, e-posta, mesaj)
3. **Bu veriyle ne yapılması gerekiyor?** (Kaydet, bildir, cevap ver)
4. **Hangi sırayla yapılmalı?** (Önce kaydet, sonra bildir, sonra teşekkür e-postası)
5. **Hata olursa ne olmalı?** (İleri seviye konu — Bölüm 13'te ele alacağız)

Bu beş soruyu her otomasyon projesinde kendinize sorduğunuzda, workflow'unuzu kağıt üzerinde tasarlamak çok daha kolay hale gelir.

---

## Bölüm 11: Yapay Zeka ile n8n — Akıllı Otomasyonlar

n8n'in son yıllardaki en büyük gelişimi, **yapay zeka modellerini (LLM - Large Language Model)** doğrudan workflow'lara entegre edebilme yeteneğidir. Bu, otomasyonlarınızı sadece "mekanik" işlerden çıkarıp, **"düşünme" gerektiren** işlere de taşımanızı sağlar.

### 11.1 LLM Nedir? (Çok Basit Anlatım)

LLM (Large Language Model - Büyük Dil Modeli), ChatGPT, Claude, Gemini gibi yapay zeka sistemlerinin temelini oluşturan teknolojidir. Bu modeller, kendilerine verilen bir metni "anlayıp", insan gibi bir cevap üretebilirler.

Örneğin bu modele "Bu e-postanın konusu fatura mı, şikayet mi, yoksa genel bir soru mu?" diye sorarsanız, e-postanın içeriğini okuyup size "Bu bir şikayet" gibi bir cevap verebilir. İşte bu yetenek, otomasyonlarımıza dahil edilebilir.

### 11.2 n8n'de AI Node'ları

n8n'de yapay zeka ile çalışmak için birkaç farklı node türü vardır:

**OpenAI / Anthropic / Google Gemini Node'ları:** Bu node'lar, doğrudan ilgili yapay zeka şirketinin API'sine bağlanır. Bir API anahtarı gerektirir (genellikle ücretlidir, kullandığınız kadar ödersiniz).

**AI Agent Node:** Bu, n8n'in en gelişmiş AI node'udur. Bir "yapay zeka ajanı" oluşturmanızı sağlar — bu ajan, sadece soru-cevap yapmaz, aynı zamanda **diğer node'ları "araç" (tool) olarak kullanabilir**. Örneğin, ajan "bu müşterinin siparişini kontrol etmem gerekiyor" diye düşünür, Google Sheets'ten veri çeker, sonucu yorumlar ve cevap verir — tüm bunlar otomatik.

**Ollama Node:** Eğer kendi bilgisayarınızda/sunucunuzda ücretsiz, açık kaynaklı yapay zeka modelleri (Llama, Mistral gibi) çalıştırıyorsanız, n8n bunlarla da entegre olabilir. Bu, API maliyetlerinden kaçınmak isteyenler için idealdir.

### 11.3 Örnek Senaryo: Yapay Zeka ile E-posta Sınıflandırma

Diyelim ki işletmenize günde 50-100 e-posta geliyor ve bunların hangisinin "öncelikli" olduğunu manuel olarak belirlemek çok zaman alıyor. İşte yapay zeka destekli bir çözüm:

```
Gmail Trigger (yeni e-posta geldiğinde)
    ↓
AI Node (e-postayı oku, şu kategorilerden birine ata:
         "Acil", "Normal", "Spam", "Bilgi Talebi")
    ↓
Switch Node (kategoriye göre)
    ├── "Acil" → Telegram'dan anlık bildirim + Gmail'de "Acil" etiketi
    ├── "Normal" → Gmail'de "Genel" etiketi
    ├── "Spam" → Otomatik arşivle
    └── "Bilgi Talebi" → AI'dan otomatik cevap taslağı oluştur
```

Bu sistemde AI node'una verilecek "prompt" (talimat) şuna benzer olabilir:

```
Aşağıdaki e-postayı oku ve sadece şu kategorilerden birini yaz, 
başka hiçbir şey yazma: Acil, Normal, Spam, Bilgi Talebi.

E-posta konusu: {{ $json.subject }}
E-posta içeriği: {{ $json.body }}
```

Yapay zeka, bu talimata göre tek bir kelime ("Acil" gibi) döndürecek ve Switch node bu kelimeye göre doğru yola yönlendirecektir.

### 11.4 Önemli Uyarı: Yapay Zeka Maliyetleri

OpenAI, Anthropic (Claude), Google gibi şirketlerin API'leri, **kullanım bazlı ücretlendirme** yapar. Yani her bir "istek" (her bir e-posta analizi gibi) küçük bir maliyet oluşturur. Bu maliyetler genellikle çok düşüktür (bir istekte birkaç kuruş), ama günde yüzlerce/binlerce işlem yapan otomasyonlarda toplam maliyet birikebilir. Otomasyonunuzu kurarken, beklenen kullanım hacmini düşünüp, bütçenize uygun model seçimi yapmanız (örneğin daha küçük/ucuz modeller kullanmak) önemlidir.

---

## Bölüm 12: Sık Kullanılan Uygulama Entegrasyonları

n8n'de en sık kullanılan entegrasyonları kısaca tanıyalım, böylece kendi senaryolarınızı kurarken hangi node'a bakmanız gerektiğini bilirsiniz.

### 12.1 Google Workspace Entegrasyonları

**Google Sheets:** Tablo verisi okuma, satır ekleme, güncelleme, silme. Bir "veritabanı" gibi kullanılabilir — özellikle teknik bilgisi olmayanlar için harika bir başlangıç noktasıdır.

**Google Drive:** Dosya yükleme, indirme, klasör oluşturma, dosya arama.

**Gmail:** E-posta okuma, gönderme, etiketleme, arşivleme, taslak oluşturma.

**Google Calendar:** Etkinlik oluşturma, listeleme, güncelleme — randevu sistemleri için idealdir.

**Google Docs:** Belge oluşturma ve düzenleme.

### 12.2 İletişim ve Mesajlaşma

**Telegram:** Ücretsiz, hızlı kurulan bot sistemi. Kişisel bildirimler için en pratik seçenektir.

**Slack:** Şirket içi takım iletişimi için. Kanal mesajları, doğrudan mesajlar, dosya paylaşımı.

**WhatsApp Business API:** Müşterilerle WhatsApp üzerinden otomatik mesajlaşma (kurulumu biraz daha karmaşıktır, Meta'nın onayını gerektirir).

**Discord:** Topluluk yönetimi, sunucu bildirimleri için.

**SMTP / Email:** Herhangi bir e-posta sağlayıcısı (kendi sunucunuz dahil) üzerinden e-posta gönderme.

### 12.3 Sosyal Medya

**Twitter/X, LinkedIn, Facebook, Instagram:** İçerik paylaşımı, otomatik gönderi zamanlama (bazı platformlarda API kısıtlamaları olabilir, dikkatli inceleyin).

**YouTube:** Video bilgisi çekme, yorum yönetimi.

### 12.4 Proje Yönetimi ve CRM

**Notion:** Veritabanı (database) sayfalarına otomatik kayıt ekleme, güncelleme — kişisel not sistemleri, içerik takvimleri için popülerdir.

**Airtable:** Notion'a benzer, tablo tabanlı esnek veritabanı.

**Trello, Asana, ClickUp:** Görev (task) oluşturma, durum güncelleme.

**HubSpot, Pipedrive:** Müşteri/satış yönetimi (CRM) sistemleri — yeni potansiyel müşteri kaydı, takip otomasyonu.

### 12.5 E-ticaret ve Ödeme

**Shopify, WooCommerce:** Sipariş bilgisi çekme, stok güncelleme, müşteri bildirimleri.

**Stripe, PayPal:** Ödeme bildirimleri, fatura oluşturma.

### 12.6 Veri ve Dosya İşleme

**RSS Feed Read:** Haber sitelerinden, bloglardan otomatik içerik çekme.

**Spreadsheet File:** Excel (.xlsx), CSV dosyalarını okuma/yazma.

**Compression:** Dosyaları sıkıştırma/açma (zip).

**FTP/SFTP:** Sunucular arası dosya transferi.

---

## Bölüm 13: Hata Yönetimi ve Güvenilirlik

Otomasyonlarınız çalışmaya başladığında, er ya da geç bir şeyler ters gidecektir — bir API geçici olarak yanıt vermeyebilir, bir veri beklediğiniz formatta gelmeyebilir, bir credential süresi dolabilir. İyi bir otomasyon, bu durumları öngörür ve yönetir.

### 13.1 Error Trigger Workflow

n8n'de özel bir workflow türü vardır: **Error Trigger**. Bu, başka bir workflow'da hata oluştuğunda otomatik olarak tetiklenen bir "acil durum" workflow'udur.

**Kurulum mantığı:**
1. Ayrı bir workflow oluşturun, adını "Hata Bildirimi" yapın.
2. İlk node olarak "Error Trigger" ekleyin.
3. Sonrasına bir Telegram veya e-posta node'u ekleyerek "Bir workflow'da hata oluştu: {{ $json.workflow.name }}" gibi bir bildirim gönderin.
4. Bu workflow'u aktif edin.
5. Diğer workflow'larınızın ayarlarında ("Settings" sekmesi), "Error Workflow" olarak bu workflow'u seçin.

Artık herhangi bir otomasyonunuzda bir hata olduğunda, anında haberdar olursunuz — gece yarısı bir otomasyonunuz sessizce durmuş olsa bile, sabah fark edersiniz.

### 13.2 Try/Catch Mantığı — "Continue on Fail"

Bazı node'ların ayarlarında "Continue on Fail" (Hata Olsa Da Devam Et) seçeneği bulunur. Bu açıkken, o node hata verse bile workflow durmaz, devam eder. Bu, özellikle "olmasa da sorun değil ama olursa iyi olur" türündeki işlemler için kullanışlıdır (örneğin bir bildirim gönderme adımı başarısız olsa da, ana işlemin (veriyi kaydetme gibi) tamamlanmasını istiyorsanız).

### 13.3 Veri Doğrulama (Validation)

Bir otomasyonun en sık karşılaştığı sorun, **beklenmeyen veridir**. Örneğin bir form, "e-posta" alanını boş bırakarak gönderilmiş olabilir. IF node'larını kullanarak, işleme başlamadan önce verinin "geçerli" olup olmadığını kontrol etmek iyi bir alışkanlıktır:

```
Webhook'tan veri geldi
    ↓
IF: email alanı boş mu?
    ↓ (Evet/Boş)              ↓ (Hayır/Dolu)
İşlemi durdur, log tut    Normal işleme devam et
```

### 13.4 Loglama ve İzleme

n8n'de "Executions" (Çalıştırmalar) sekmesi, her workflow'un her çalışmasının kaydını tutar. Burada:

- Hangi workflow'un ne zaman çalıştığını
- Başarılı mı yoksa hatalı mı olduğunu
- Her node'da hangi verinin işlendiğini

görebilirsiniz. Bir otomasyonunuz "beklediğim gibi çalışmıyor" dediğinizde, ilk bakacağınız yer burasıdır. Her node'a tıklayarak, o anki veriyi inceleyebilir ve sorunun nerede olduğunu adım adım takip edebilirsiniz.

---

## Bölüm 14: İleri Seviye İpuçları ve En İyi Uygulamalar

### 14.1 Workflow'ları Anlamlı İsimlendirin

"İsimsiz İş Akışı 1", "İsimsiz İş Akışı 2" gibi isimlerle 20 workflow'unuz olduğunda, hangisinin ne işe yaradığını hatırlamak kabus olur. Her workflow'a, ne yaptığını anlatan açık isimler verin: "Müşteri Formu → Sheets + Telegram", "Günlük Hava Durumu Bildirimi", "Haftalık Rapor Gönderimi" gibi.

### 14.2 Sticky Notes (Yapışkan Notlar) Kullanın

n8n canvas'ına "Sticky Note" ekleyebilirsiniz — bunlar, workflow'unuzun içine yazdığınız açıklama kutularıdır. Karmaşık bir workflow'u 6 ay sonra açtığınızda, "bu node ne işe yarıyordu?" diye düşünmek yerine, notlarınızı okuyarak hemen hatırlarsınız.

### 14.3 Küçük Parçalar Halinde Test Edin

Büyük bir workflow'u baştan sona tek seferde test etmeye çalışmayın. Her node'u ekledikten sonra "Test step" (o node'u tek başına çalıştırma) özelliğini kullanarak, o adımın doğru çalıştığından emin olun, sonra bir sonraki node'a geçin. Bu yaklaşım, hatayı bulmayı çok kolaylaştırır.

### 14.4 Hassas Bilgileri Asla Sabit (Hardcoded) Yazmayın

API anahtarlarını, şifreleri, gizli bilgileri doğrudan node'ların içine yazmak yerine, her zaman "Credentials" sistemini kullanın. Bu sadece güvenlik için değil, aynı zamanda workflow'unuzu paylaşmanız gerektiğinde (örneğin bir meslektaşınızla) hassas bilgilerin sızmasını önler.

### 14.5 Workflow'larınızı Yedekleyin

n8n'de workflow'larınızı **JSON dosyası olarak dışa aktarabilirsiniz** (Export). Bu, hem bir yedekleme yöntemidir hem de workflow'larınızı başka bir n8n kurulumuna taşımanın (Import) yoludur. Önemli otomasyonlarınızı düzenli olarak dışa aktarıp güvenli bir yere kaydetmek, "n8n sunucum bozuldu, her şeyi kaybettim" senaryosundan sizi korur.

### 14.6 Şablonlardan (Templates) Öğrenin

n8n'in sol menüsünde "Templates" bölümü, dünya çapındaki kullanıcıların paylaştığı binlerce hazır otomasyon örneğini içerir. Yeni bir şey kurmadan önce, benzer bir şablon olup olmadığına bakmak, hem zaman kazandırır hem de "bu nasıl yapılıyormuş" diye öğrenmenizi sağlar. Bir şablonu içe aktarıp, kendi credential'larınızı bağlayarak hızlıca kullanabilirsiniz.

### 14.7 "Pinned Data" ile Geliştirme Hızınızı Artırın

Bir node'un çıktısını "pin" (sabitleyebilirsiniz) — bu, o node'u her test ettiğinizde gerçekten çalıştırmak yerine, daha önce aldığı sonucu "dondurup" kullanmanızı sağlar. Özellikle Webhook gibi "her seferinde yeniden tetiklenmesi gereken" node'larla çalışırken, sonraki node'ları test ederken zamandan büyük tasarruf sağlar.

---

## Bölüm 15: Sık Sorulan Sorular (SSS)

**S: n8n kullanmak için kod bilmem gerekiyor mu?**

C: Hayır. n8n'in temel kullanımı tamamen görsel, sürükle-bırak mantığıyla çalışır. Kod bilgisi (JavaScript), sadece çok özel/karmaşık ihtiyaçlarınız olduğunda (Code node ile) işinize yarar, ama bu rehberdeki örneklerin %90'ı hiç kod yazmadan yapılabilir.

**S: n8n tamamen ücretsiz mi?**

C: Kendi bilgisayarınızda veya kendi sunucunuzda çalıştırırsanız (self-hosted), kişisel/iç kullanım için tamamen ücretsizdir ve işlem sınırı yoktur. n8n Cloud (bulut sürümü) ise ücretli bir abonelik modeline sahiptir, ancak ücretsiz deneme süresi sunar.

**S: Otomasyonum çalışırken bilgisayarımı kapatırsam ne olur?**

C: Eğer n8n'i kendi bilgisayarınızda çalıştırıyorsanız ve bilgisayarı kapatırsanız, n8n da durur ve zamanlama bazlı (Schedule) veya webhook bazlı tetikleyiciler çalışmaz. 7/24 çalışan otomasyonlar için bir sunucuda (VPS) veya n8n Cloud'da barındırma gerekir.

**S: Bir otomasyon kurarken hangi node'u kullanacağımı nasıl bileceğim?**

C: n8n'in node arama paneline, ne yapmak istediğinizi (örneğin "PDF", "Excel", "WhatsApp") yazın. Çoğu zaman ihtiyacınız olan node doğrudan çıkar. Eğer çıkmazsa, "HTTP Request" node'u ile o servisin API'sine doğrudan bağlanabilirsiniz (bu daha teknik bir yoldur).

**S: Verilerim güvende mi?**

C: Eğer n8n'i kendi sunucunuzda barındırıyorsanız, tüm verileriniz (workflow'larınız, credential'larınız, çalıştırma geçmişiniz) tamamen sizin kontrolünüzdedir, hiçbir üçüncü tarafa gitmez. n8n Cloud kullanıyorsanız, n8n şirketinin gizlilik politikalarına tabi olursunuz.

**S: Bir workflow'u nasıl başkalarıyla paylaşırım?**

C: Workflow'unuzu "Export" (JSON olarak dışa aktarma) yaparak bir dosya elde edersiniz. Bu dosyayı paylaşabilirsiniz, karşı taraf da "Import" ile kendi n8n'ine yükleyebilir. Ancak credential'lar (API anahtarları vb.) bu dosyaya dahil olmaz — her kullanıcı kendi credential'larını ayrıca tanımlamalıdır (bu, güvenlik için iyidir).

**S: n8n öğrenmek ne kadar zaman alır?**

C: Bu rehberdeki temel kavramları (tetikleyici, node, bağlantı, expression) anladıktan sonra, basit otomasyonları (e-posta bildirimleri, tablo güncellemeleri gibi) bir-iki saat içinde kurabilirsiniz. Daha karmaşık projeler (AI entegrasyonu, çok adımlı iş akışları) için pratik yaparak birkaç hafta içinde oldukça yetkin hale gelirsiniz. En önemlisi: **denemekten korkmayın**. n8n'de yanlış bir bağlantı kurmanın "bedeli" yoktur — istediğiniz zaman silip yeniden deneyebilirsiniz.

**S: Hangi otomasyonla başlamalıyım?**

C: Kendi günlük hayatınızdan, "her gün/her hafta tekrar ettiğim ve canımı sıkan" basit bir görev seçin. Örneğin: "Her sabah hava durumuna bakıp giyineceğim kıyafeti seçiyorum — bunun yerine her sabah otomatik bir hava durumu mesajı alabilir miyim?" gibi küçük ve kişisel bir hedefle başlamak, motivasyonunuzu yüksek tutar ve öğrenme sürecini hızlandırır.

---

## Bölüm 16: Sonuç ve Sonraki Adımlar

Bu rehberde, n8n'in ne olduğundan başlayarak, kurulumunu, temel arayüzünü, ilk otomasyonunuzu, tetikleyicileri, kimlik bilgilerini, temel veri işleme node'larını, ifadeleri (expressions), gerçek bir proje örneğini, yapay zeka entegrasyonunu, sık kullanılan uygulamaları, hata yönetimini ve ileri seviye ipuçlarını adım adım, sıfırdan anlattık.

Şimdi elinizde şu beceriler var:

- n8n'i kurabilir ve çalıştırabilirsiniz
- Tetikleyici ve aksiyon mantığını anlıyorsunuz
- Node'ları birbirine bağlayıp veri akışı oluşturabilirsiniz
- JSON verisini okuyup anlayabilirsiniz
- Expression (ifade) sistemi ile dinamik değerler kullanabilirsiniz
- Telegram, Google Sheets, Gmail gibi popüler servisleri bağlayabilirsiniz
- Koşullu mantık (IF, Switch) ile akıllı dallanmalar kurabilirsiniz
- Yapay zeka modellerini otomasyonlarınıza entegre edebilirsiniz
- Hataları yönetebilir ve otomasyonlarınızı güvenilir kılabilirsiniz

### Sonraki Adımlar İçin Önerilerimiz

1. **Küçük bir kişisel otomasyon kurun.** Örneğin, her sabah size hava durumunu Telegram'dan gönderen bir workflow. Bu, tüm temel kavramları pratiğe dökmenizi sağlar.

2. **n8n'in resmi şablon kütüphanesini (Templates) keşfedin.** Binlerce hazır örnek, fikir almak ve "bunlar nasıl yapılmış" diye öğrenmek için harika bir kaynaktır.

3. **Topluluk forumlarına göz atın.** n8n'in aktif bir kullanıcı topluluğu var; takıldığınız noktalarda büyük ihtimalle aynı sorunu yaşamış birini bulabilirsiniz.

4. **Adım adım büyüyün.** İlk otomasyonunuz mükemmel olmak zorunda değil. Önemli olan, çalışan bir şeyi tamamlamak ve oradan geliştirmektir. Her yeni proje, öncekinden daha hızlı ve daha rahat kurulacaktır.

5. **İş akışlarınızı dokümante edin.** Sticky Notes kullanarak, her workflow'un ne işe yaradığını, hangi servislere bağlı olduğunu not edin. Gelecekte kendinize (veya ekibinize) büyük bir iyilik yapmış olursunuz.

Otomasyon, bir kere "mantığını" kavradığınızda, hayatınızın birçok alanında zaman kazanmanızı sağlayan güçlü bir araç haline gelir. n8n, bu yolculuğa başlamak için hem ücretsiz hem de son derece esnek bir platform sunuyor. Şimdi sıra sizde — ilk otomasyonunuzu kurun, deneyin, hata yapın, öğrenin ve geliştirin.

**Başarılar dileriz!**

---

*Bu rehber, Toprak Ahmet Aydoğmuş — Siber Akademi tarafından, sıfır teknik bilgiye sahip kullanıcıların n8n ile otomasyon dünyasına güvenle adım atabilmesi için hazırlanmıştır.*
