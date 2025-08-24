Türkçe için UMR Etiketleme Rehberi
=======================================================


Bu rehber, Türkçe cümlelerin Universal/Uniform Meaning Representation (UMR) ile etiketlenmesi için kapsamlı bir şablon sunar.

## İçindekiler
- [Giriş](#giriş)
- [UMR ve AMR Arasındaki Farklar](#umr-ve-amr-arasındaki-farklar)
- [Evrensel Kavram Envanteri](#evrensel-kavram-envanteri)
- [Morfolojik Esneklik](#morfolojik-esneklik)
- [Görünüş, Kip ve Kapsam Anotasyonu](#görünüş-kip-ve-kapsam-anotasyonu)
- [Belge Düzeyinde Anlam İlişkileri](#belge-düzeyinde-anlam-ilişkileri)
- [Düşük Kaynaklı Dil Desteği ve Aşamalı Sözlük Oluşturma](#düşük-kaynaklı-dil-desteği-ve-aşamalı-sözlük-oluşturma)
- [Türkçeye Özgü Etiketleme Kuralları](#türkçeye-özgü-etiketleme-kuralları)
- [Kavram Seçimi ve Çerçeve Sözlüğü](#kavram-seçimi-ve-çerçeve-sözlüğü)
- [İlişkiler ve Roller](#ilişkiler-ve-roller)
- [Zamirler ve Gizli Özne/Nesne (Pro‑Drop)](#zamirler-ve-gizli-öznenesne-pro-drop)
- [Fiil Çatıları: Etken, Edilgen ve Ettirgen](#fiil-çatılar-etken-edilgen-ve-ettirgen)
- [Zaman ve Görünüş (Tense ve Aspect) İşaretleme](#zaman-ve-görünüş-tense-ve-aspect-i̇şaretleme)
- [Kiplik ve Modalite (Mode ve Modality)](#kiplik-ve-modalite-mode-ve-modality)
- [Niceliksel İfadeler ve Kapsam](#niceliksel-i̇fadeler-ve-kapsam)
- [Özel Adlar ve Ad Tamlamaları](#özel-adlar-ve-ad-tamlamaları)
- [Deyimsel ve Mecazi İfadeler](#deyimsel-ve-mecazi-i̇fadeler)
- [Cümleler Arası Bağlantılar (Belge Düzeyi)](#cümleler-arası-bağlantılar-belge-düzeyi)
- [Örnek Anotasyonlar](#örnek-anotasyonlar)
- [Kaynaklar](#kaynaklar)

---
## Giriş
Universal/Uniform Meaning Representation (UMR), cümlelerin anlamını dil bağımsız biçimde grafiksel olarak temsil etmeyi amaçlayan bir anlamsal gösterim formatıdır. UMR, Abstract Meaning Representation (AMR) modelini temel alır ancak onu genişleterek farklı dillerin dilbilimsel özelliklerini daha evrensel bir şema altında ifade edebilmeyi hedefler. Başlangıçta AMR, İngilizceye özgü bir anlam temsili olarak geliştirilmiştir; diğer dillere uyarlamak için dil‑özel kurallar belirlemek gerekmiştir. Nitekim Türkçe gibi eklemeli (aglütine) ve serbest söz dizimine sahip, öznenin sıkça gizlenebildiği (pro‑drop) diller, İngilizce AMR şemasından yapısal olarak ayrışan durumlar sergiler. Bu nedenle, Türkçe için AMR etiketleme kılavuzu hazırlanmış ve Türkçeye özgü fenomenler belirlenerek çözüm önerileri sunulmuştur. UMR ile birlikte ise, anlam gösteriminin diller arası bir örneklem haline gelmesi hedeflenmektedir. UMR, düşük kaynaklı diller dahil olmak üzere çeşitli dillerde anlamın tutarlı biçimde temsilini sağlamak, ve mantıksal çıkarım için gerekli kiplik (modality), görünüş (aspect), niceliklendirme (quantification) ve kapsam (scope) bilgilerini graf içine entegre etmek üzere AMR şemasını genişletir. Ayrıca UMR, yalnızca tek cümle düzeyinde kalmayıp, belge düzeyinde cümleler arası zamansal ve modal ilişkileri ile özne/nesne bağıntılarını (coreference) da gösterim kapsamına alır. Bu kılavuzda, mevcut Türkçe AMR kılavuzunun yapısını temel alarak, UMR'nin getirdiği yeniliklerin Türkçe özelinde nasıl uygulanacağını ele alıyoruz. Amaç, sıfırdan etiketleme yapacak birine yol gösterecek açıklayıcı bir şablon sunmaktır. Örnek Türkçe cümleler üzerinden, Türkçe’nin morfolojik ve anlamsal özelliklerini UMR grafına yansıtma prensiplerini açıklıyoruz.

## UMR ve AMR Arasındaki Farklar

UMR şemasını Türkçe’ye uyarlamadan önce, AMR ile UMR arasındaki temel farkları vurgulamak yararlı olacaktır:

## Evrensel Kavram Envanteri

AMR, kavramları tanımlarken büyük ölçüde İngilizce PropBank ve FrameNet gibi İngilizceye özgü sözcük anlam envanterlerine dayanırdı. UMR ise dil bağımlılığını azaltmak adına İngilizce PropBank’ten uzaklaşıp yerine VerbAtlas çerçevelerini ve BabelNet kavram envanterini kullanarak daha dil‑dil bağımsız bir çözüm sunar. Bu sayede farklı dillerde ortak kavram setleri üzerinden anlam karşılaştırması yapmak mümkün hale gelir.

## Morfolojik Esneklik

Türkçe gibi dillerde tek bir kelime birçok ek alarak kompleks anlamlar taşıyabilir (örneğin “geldiyseniz” kelimesinde zaman, kişi ve şart ekleri mevcut). AMR’de bu tür biçimbirimsel yapıların nasıl ayrıştırılacağı dil‑özel kararlara bırakılıyordu. UMR, her bir sözcüğü anlam birimlerine ayırma konusunda esneklik tanır: Morfosentaktik olarak karmaşık kelimelerin ayrı morfemlere bölünmesini zorunlu tutmaz, ancak gerektiğinde tutarlılık için bunu yapmaya olanak tanır. Başka bir deyişle, polisentetik veya eklemeli bir dilde tek bir sözcük birden çok kavramı içeriyorsa, UMR bunu tek bir düğüm olarak da temsil edebilir, uygun görüldüğünde ayrı kavramlara da ayrıştırabilir. Bu yaklaşım, dilin yapısına uygun en anlaşılır gösterimi seçme imkânı sağlar.

## Görünüş, Kip ve Kapsam Anotasyonu

UMR, cümle düzeyinde gramatikal görünüş (aspect), kiplik gücü (modal strength) ve niceleyici kapsamı (quantifier scope) gibi bilgileri açıkça graf üzerinde işaretler. AMR’de genellikle bu ayrıntılar gösterime dahil edilmezken, UMR bunları ayrı nitelikler olarak ekler. Örneğin, UMR’de yüklemlere beş temel kategoriden birinde :aspect etiketi verilir (örn. Performance, State, Habitual, Endeavor, Activity) ve bu şekilde eylemin gerçekleşme türü belirtilir. Benzer şekilde, kesinlik veya gereklilik ifadeleri :modstr (modal strength) özelliği ile tam, kısmi ya da nötr olarak (olumlu/olumsuz şeklinde) derecelendirilir. Ayrıca bir cümlede birden fazla niceleyici veya olumsuzluk söz konusuysa, bunların mantıksal kapsam sırasını belirtmek için gerekiyorsa graf yapısına özel bir scope düğümü eklenebilir. Bu detaylı işaretlemeler, cümlenin mantıksal yorumunu kolaylaştırmayı hedefler.

## Belge Düzeyinde Anlam İlişkileri

AMR temel olarak her cümleyi bağımsız bir anlam grafı olarak ele alırken, UMR aynı zamanda birden fazla cümle arasındaki ilişkileri de modelleyebilir. Özellikle metin içerisindeki olaylar arası zaman ilişkileri (:before, :after gibi), öznellik/modallik ilişkileri (bir söylemin kimin bakış açısıyla kesin/şüpheli olduğu) ve yeniden özdeşleme (coreference) bağları UMR içinde gösterilebilir. Örneğin, birden fazla cümlede geçen aynı varlığı UMR grafında tek bir özne olarak bağlamak mümkündür; ya da bir cümlede bahsedilen bir olayın diğer bir cümlenin olayıyla zaman ilişkisi (ör. önce/sonra) belirtilebilir. Bu belge düzeyi anotasyonlar, cümle düzeyindekilere kıyasla daha ayrıntılı bilgi sağlayarak, örneğin yazarın bir olaya kesin gözüyle mi baktığı yoksa başkasından duyduğu için emin olmadığını bile graf üzerinden ifade edebilmeyi sağlar.

## Düşük Kaynaklı Dil Desteği ve Aşamalı Sözlük Oluşturma

UMR, dil kaynaklarının kısıtlı olduğu senaryolara uygun bir çerçeve sunar. Eğer bir dil için hazır anlamsal çerçeve envanteri yoksa, UMR kılavuzu Aşama 0 (Stage 0) dediğimiz yöntemle, doğrudan cümledeki kelimelerin kavram olarak seçilip geçici bir sözlük oluşturulmasına imkân tanır. Bu aşamada dil‑evrensel katılımcı rol etiketleri (örn. Actor, Patient gibi) kullanılır. Zamanla o dil için yeterli sayıda örnek biriktikçe ve dil‑özel çerçeve listeleri çıkarıldıkça, Aşama 1 (Stage 1) dediğimiz tam çerçeve envanterine geçilebilir ve bu noktada her eylem için dil‑özel (veya çapraz dilsel) rol setleri kullanılır. Türkçe, halihazırda Turkish PropBank gibi bir kaynağa sahip olduğu için, UMR etiketlemesinde doğrudan bu mevcut çerçeve envanterinden yararlanmak mümkündür.

## Türkçe'ye Özgü Etiketleme Kuralları

Türkçenin dilbilgisel özellikleri, UMR grafına yansıtılırken belirli uyarlamalar gerektirir. Türkçe morfolojik olarak zengin, eklemeli ve özne düşümlü (pro‑drop) bir dildir; söz dizimi İngilizceye kıyasla daha serbesttir. Aşağıda, Türkçe cümleleri UMR ile etiketleyecek birinin ihtiyaç duyacağı kılavuz niteliğindeki temel kurallar ve örnek durumlar açıklanmaktadır.

## Kavram Seçimi ve Çerçeve Sözlüğü

UMR grafında her anlam birimi bir kavram düğümü (concept node) ile temsil edilir. Türkçe cümleleri etiketlerken:
•	Fiiller (Eylemler) – Mümkün olduğunda Türkçe için hazırlanmış PropBank çerçevelerindeki tanımları kullanın. Örneğin “gitmek” fiili için git-01 gibi bir rol seti tanımı mevcutsa, graf düğümünü (g / git-01) şeklinde oluşturun. Bu, ilgili eylemin birincil anlamını temsil eder. Eğer PropBank çerçevesinde yoksa veya düşük kaynaklı bir fiil ise, UMR yaklaşımıyla Stage 0 anotasyonu yapılabilir: fiilin kök halini (örn. "uçmak" fiili için "uçmak") kavram olarak kullanıp, ona uygun argüman rollerini genel (Actor, Undergoer vs.) olarak atayabilirsiniz. Sonradan bu fiil için rol seti tanımlandığında grafik güncellenebilir.
•	İsimler ve Sıfatlar – Türkçe’de isim ve sıfatlar için genellikle ayrı bir çerçeve envanteri bulunmaz. Bu durumda, kavram düğümü olarak ilgili ismin ya da sıfatın kök hali kullanılır. Örneğin “öğrenci” kelimesi bir kavram olarak (ö / öğrenci) biçiminde grafa girilir. Bu kavramın İngilizce karşılığı "student" olsa da, UMR dil bağımsız bir kavram envanteri hedeflediğinden, Türkçe metinler için Türkçe kök tercih edilebilir. Eğer kavramın BabelNet gibi bir sözlükte karşılığı biliniyorsa ve projenizin amacı çapraz dil tutarlılığı ise, bu idare edilebilir. Önemli olan, her kavram düğümünün anlamsal olarak doğru bir lemmaya denk gelmesidir; kelimenin aldığı çekim ekleri bu düğüm ismine yansıtılmaz (çekimler ayrı olarak niteliklerde gösterilecektir).
•	Çok Kelimeli İfadeler – Türkçede birleşik fiiller veya deyimler (örn. “el ele vermek”, “kafayı yemek”) gibi birden fazla kelimeden oluşup tek bir anlam veren ifadeler tek bir kavram olarak ele alınabilir. UMR kılavuzuna göre, birden fazla kelimenin birleşerek tek kavram oluşturması, dil bazında kararlaştırılır ve tutarlı uygulanır. Örneğin “hak etmek” ifadesi soyut bir eylem olarak tek bir hak_et-01 kavramı şeklinde temsil edilebilir. Buna karşın “tahta kapı” gibi bir isim tamlamasında ayrı bir kavram oluşturmak yerine “kapı” kavramına bir niteleyici ilişki eklemek (bkz. İlişkiler bölümü) tercih edilir. Hangi çok kelimeli ifadelerin birleşik kavram sayılacağı konusunda tutarlı örnekler belirlemek faydalı olacaktır.
•	Özel İsimler (Varlıklar) – Kişi, yer, kurum isimleri gibi özel adlar UMR’de tıpkı AMR’de olduğu gibi ayrı bir yapı ile gösterilir. Bir özel isim iki parçalı bir yapıyla ifade edilir: önce genel bir tür kavramı, ardından :name rolü ile adın kendisi. Örneğin “Ayşe” için (p / person :name (n / name :op1 "Ayşe")) biçiminde bir gösterim kullanılır. Burada person genel varlık türünü, iç içe geçmiş name düğümü ise gerçek ismi tutar. Eğer mümkünse ve gerekli görülürse, özel isme bir de :wiki özelliği eklenerek ilgili Vikipedi sayfasına işaret edilebilir (örn. :wiki "Ayşe_(şarkıcı)"). Ancak :wiki etiketi tercihe bağlı meta‑bilgi olup, esas grafik yapıyı etkilemez.

## İlişkiler ve Roller

Kavram düğümleri arasındaki anlamsal bağlar, ilişki etiketleri ile gösterilir. UMR’de ilişkiler iki kategoriye ayrılabilir:

•	Katılımcı Roller (Participant Roles) – Bir eylemin çekirdek argümanlarını ifade eden rollerdir. Türkçe UMR etiketlemesinde, eğer Turkish PropBank’te ilgili fiil için Arg0, Arg1, Arg2... tanımları varsa bunları kullanın. Örneğin git-01 fiili için Arg0 “giden” (actor), Arg1 “gidilen yer” (goal) olarak tanımlanmışsa, “Ali okula gitti” cümlesinin grafında (git-01 :ARG0 (p / person :name "Ali") :ARG1 (o / okul)) şeklinde bir yapı olmalıdır. Böylece her ArgX rolü fiilin anlamına göre doğru öğeye bağlanır. Eğer PropBank tanımı yoksa veya Stage 0 modunda anotasyon yapılıyorsa, UMR’nin evrensel rol etiketlerinden yararlanılır. Örneğin, deneyim bildiren bir fiilde Arg0/Arg1 bilinmiyorsa, yerine :Experiencer, :Stimulus gibi daha genel roller kullanılabilir. Bu rollerin listesi ve tanımları geliştikçe kılavuza eklenebilir.

•	Diğer Semantik İlişkiler – Çekirdek argüman olmayan diğer bağlantılar uygun anlamsal ilişki etiketleriyle gösterilir. Örneğin:

•	Zaman belirteçleri için :temporal etiketi kullanılır. “Dün geldi” cümlesinde (g / gel-01 :ARG0 (p / person :name "Ali") :temporal (d / dün)) şeklinde :temporal ile zaman ifadesi bağlanır. (Not: AMR’de kullanılan :time yerine UMR kılavuzu :temporal terimini tercih etmektedir.)

•	Yer/mekan belirteçleri için :location ilişkisi kullanılabilir. “Okulda” ifadesi, uygun olduğu durumda (o / okul :location-of (e / etkinlik)) gibi bağlanabilir veya fiile :location rolüyle eklenebilir.

•	Amaç veya niyet bildiren yan tümceler için :purpose (ya da çatı fiilinin tanımına göre Arg2) ilişkisi kullanılabilir. Örneğin “Toplantıya katılmak için geldi” cümlesinde, gel-01 fiiline :purpose rolüyle ikinci eylem grafı bağlanabilir.

•	Koşul bildiren yapılar (–"‑se", “eğer”–) için :condition, biçimsel olmayan ek bilgiler için :mode (soru, emir gibi, aşağıda anlatılacak) kullanılabilir.

•	Sahiplik bildirimi için :poss etiketi yaygın biçimde kullanılır. “Ali’nin kitabı” ifadesini (k / kitap :poss (p / person :name "Ali")) şeklinde temsil edebiliriz. Bu durumda :poss ilişkisi kitabın kime ait olduğunu gösterir. (Alternatif olarak “Ali have book” anlamında bir have-03 fiili de kullanılabilirdi; ancak isim tamlamalarında :poss doğrudan tercih edilebilir.)

•	Birden fazla öğeyi sıralamak için :op1, :op2 … şeklinde sıralama rolleri kullanılır. Özellikle “veya”, “ve” gibi bağlaçlarla ayrılan listelerde veya name yapısında isim parçalarını sırayla göstermek için bu numaralandırılmış rolleri kullanırız.

•	Nicelik (sayısal değer) belirtmek için :quant ve :unit kullanılır. “5 kitap” ifadesi (k / kitap :quant 5) şeklinde, “2 litre su” ifadesi ise (s / su :quant 2 :unit (l / litre)) şeklinde ifade edilir. Ayrıca sıra belirtmek için :ord (ordinal) ve aralık belirtmek için :range gibi etiketler UMR’de tanımlıdır. Örneğin “ilk defa” ifadesinde ilk kavramı (o / ordinal-entity :value 1) biçiminde gösterip ana yapıya :ord ile bağlayabiliriz.
İlişki etiketlerini seçerken hem Türkçe dil bilgisini hem de UMR’nin tutarlılık prensiplerini göz önünde bulundurun. Gereksiz ayrıntıya girmektense anlamı açıkça verecek kadar ayrıntı eklemek hedeflenmelidir.

## Zamirler ve Gizli Özne/Nesne (Pro‑Drop)

Türkçede özne (ve zaman zaman nesne) öğeleri, fiil çekimlerinden anlaşılabildiği için cümlede açıkça bulunmayabilir. UMR gösteriminde her bir anlamsal özne veya nesne graf üzerinde temsil edilmelidir; dolayısıyla cümlede eksik görünen, ancak anlamca var olan bir unsur varsa bunu uygun bir düğümle göstermeliyiz. UMR, tüm zamirleri – açık, örtük, düşmüş veya belirsiz – tek tip bir yapıyla ele alır:
•	Kişi Zamirleri: “ben, sen, o, biz, siz, onlar” gibi zamirler veya bunların cümlede hiç yazılmamış halleri, graf üzerinde genel bir person kavramı ve ilgili :ref-person ile :ref-number nitelikleriyle gösterilir. Örneğin, “(Ben) geldim.” cümlesini ele alalım. Özne “ben” düşmüş olsa da, UMR grafında bunu belirtmeliyiz:
(g / gel-01
     :ARG0 (p / person :ref-person 1st :ref-number Singular)
     :Aspect Performance
     :Modstr FullAff)

Yukarıda :ARG0 rolü altında (p / person) düğümü kullanıldı ve bu düğüme :ref-person 1st (birinci kişi) ve :ref-number Singular (tekil) özellikleri eklendi. Bu şekilde graf, yüklemin birinci tekil kişi tarafından gerçekleştirildiğini ifade eder. Dikkat: UMR bu kişi kavramının cümlede açıkça yazılmadığını ayrıca işaretlemez; yani bir (p / person) düğümü 1. tekil ise bunun düşmüş bir özne mi yoksa açıkça “ben” mi olduğu graf'tan anlaşılmaz. Önemli olan, anlamda var olan öznenin temsil edilmiş olmasıdır.

•	Üçüncü Şahıs ve Belirsiz Özneler: “o” (3. tekil) gibi zamirler de aynı şekilde (p / person :ref-person 3rd :ref-number Singular) biçiminde gösterilir. Eğer cümlede özne hiç belli değilse (örneğin edilgen bir cümlede fail belirtilmemişse), genellikle graf üzerinde o özne hiç gösterilmez. Yani, “Kapı kapandı.” cümlesinde kapıyı kimin kapadığı bilinmiyorsa ARG0 (fail) eklenmeden (kapan-01 :ARG1 (k / kapı)) şeklinde bırakılır. Ancak eğer bağlamdan belirsiz öznenin “insanlar” olduğu çıkarılabiliyorsa, istenirse (p2 / person :ref-person 3rd :ref-number Plural) gibi soyut bir fail de eklenebilir. Bu tercih anotasyon yönergesine bağlıdır; çoğunlukla belirtilmeyen ajanlar graf dışında tutulur.

•	Çoğul Kişi ve Resmî Hitap: “biz, siz, onlar” gibi çoğul şahıslar için :ref-number Plural kullanılır. Özellikle Türkçede “siz” hem 2. çoğul hem de kibar tekil hitap olabildiği için dikkat edilmelidir. Eğer bağlamdan “siz”in tek bir kişiye kibar hitap olduğu anlaşılıyorsa, graf yine :ref-number Plural, :ref-person 2nd içerir; ayrıca isteğe bağlı olarak kibar hitabı belirtmek için :mod-polite + niteliği eklenebilir. UMR’de İspanyolca örneğinde “usted” (2. tekil kibar) zamiri benzer şekilde kişi düğümüne :mod-polite + ile işaretlenmiştir. Türkçe için, eğer “Siz geldiniz.” cümlesini kibar formda analiz ediyorsak:
(g / gel-01
     :ARG0 (p2 / person :ref-person 2nd :ref-number Plural :mod-polite +)
     ...)

Çoğu durumda :mod-polite eklemeye gerek kalmayabilir, çünkü :ref-person ve :ref-number bilgileri “siz”i zaten temsil eder; ancak tekil bir kişi kastedildiği halde Plural kullanılıyorsa, bunu belirgin yapmak için bu özellik sunulmuştur.

•	İfade‑i Meram Zamirleri: Kimi zaman cümlelerde belirsiz özne olarak “insan” ya da “biz” genelinde konuşulur (“Türkçe’de böyle derler” cümlesinde özne belirsiz genel bir kitledir). Bu gibi durumlarda da (p / person) düğümü 3. çoğul yapılarak belirsiz özne temsil edilebilir. Ya da eğer gerçekten genel bir doğruluk ise, hiç özne konmadan bir olgusal ifade olarak bırakılabilir. Yönergeleriniz bu gibi sınır durumları için örnekler içermelidir.
Özetle, Türkçe’de gizli kalsa bile her özne/nesne anlamsal rolünü graf üzerinde bir düğümle temsil ediyoruz. Bu, UMR’nin tam bir anlamsal çözümleme sunabilmesi için gereklidir.

## Fiil Çatıları: Etken, Edilgen ve Ettirgen

Türkçede fiil çatılarında ekler aracılığıyla dönüşümlere uğrar. UMR gösteriminde fiilin anlamına odaklanılır, yüzeydeki dilbilgisel form arka planda bırakılır. Bu kapsamda:

•	Etken Çatı: Etken cümlelerde (failin açıkça özne olduğu durumlar) zaten standart Arg0, Arg1 atamaları yapılır. Örneğin “Öğretmen kapıyı açtı.” cümlesi için (aç-01 :ARG0 (o / öğretmen) :ARG1 (k / kapı)) şeklinde etken yapı yansıtılır. Burada ek bir işaretleme gerekmez.

•	Edilgen Çatı: Edilgen fiiller, Türkçede fiil köküne -l veya -n eki alarak yapılır (“Kapı açıldı”, “Araba yıkandı” gibi). Bu cümlelerde eylemi yapan kişi belirtilmemişse, anlamsal grafimizde o role karşılık bir düğüm yer almayabilir. Örneğin “Araba yıkandı.” ifadesini (yıka-01 :ARG1 (a / araba)) biçiminde modelleyebiliriz; Arg0 (yıkayan) yoktur çünkü bilgi mevcut değil. Eğer edilgen cümlede yapan belli ise (örn. “Araba Ali tarafından yıkandı.”), bu durumda (yıka-01 :ARG0 (p / person :name "Ali") :ARG1 (a / araba)) şeklinde Arg0ı eklemek gerekir; “tarafından” ifadesi yüzeyde kalsa da manada fail zaten Ali olduğundan ayrı bir kavram gerekmez. Edilgenliği ayrıca işaretlemek için özel bir nitelik kullanılmaz; graf yapısı zaten Arg0’ın eksikliğinden veya “by” yapısından anlaşılır.

•	Ettirgen (Causative) Çatı: Türkçede fiile -dir, -tir gibi ekler eklenerek ettirgen çatılar oluşturulur (birine bir işi yaptırmak anlamı). UMR’de bu durum, alttaki temel eylemi ve onu tetikleyen ayrı bir neden‑sonuç ilişkisini temsil edecek şekilde ayrıştırılmalıdır. Yani, tek bir kelime olsa bile anlamsal olarak iki olay vardır: birincisi yaptırma eylemi, ikincisi asıl eylemin gerçekleşmesi. Bu amaçla genellikle genel bir “cause-01” kavramı veya ilgili fiilin ettirgen versiyonu kullanılır. Örneğin “Ayşe, Mehmet’e mektubu yazdırdı.” cümlesini şöyle analiz edebiliriz:

(c / cause-01
     :ARG0 (a / person :name "Ayşe")
     :ARG1 (y / yaz-01
              :ARG0 (m / person :name "Mehmet")
              :ARG1 (m2 / mektup)))
Burada cause-01 (neden olmak) fiili üst düzeyde kullanıldı. :ARG0 işi yaptıran Ayşe, :ARG1 ise gerçekleşen eylemin kendisidir. İçerideki yaz-01 düğümü, Mehmet’in mektup yazma eylemini temsil ediyor. Alternatif olarak, eğer Turkish PropBank’te “yazdır-01” gibi ettirgen bir çerçeve tanımlanmışsa onu da kullanabilirsiniz; ancak çoğu durumda cause-01 ile ayrıştırmak, diller arası tutarlılık için tercih edilir.

•	Dönüşlü Çatı: Bazı fiiller Türkçede -l ekiyle dönüşlü (kendi kendine yapılan) anlamı kazanır (“yıkanmak” = kendini yıkamak). Bu durumda da Arg0 ve Arg1 aslında aynı varlık olur. Graf üzerinde bunu göstermek için Arg0 ve Arg1’de aynı düğüme referans verilebilir ya da sadece Arg0 bırakılıp eylemin kendine uygulandığı yorumlanabilir. Örneğin “Ali yıkandı.” (Ali kendini yıkadı) cümlesi (yıkan-01 :ARG0 (p / person :name "Ali")) şeklinde temsil edilebilir; Arg1’i ayrıca koymaya gerek olmayabilir çünkü fiilin anlamı Arg0=Arg1 durumunu içerir. Eğer belirsizlik varsa, :ARG1 p diyerek aynı kişiyi Arg1 olarak da ekleyebilirsiniz.

Özetle, fiil çatısındaki değişimler UMR grafında ayrı kavramlar veya ilişki yapıları olarak ele alınır; ancak yüzeysel ekler graf üzerine doğrudan yansıtılmaz. Bu, UMR’nin “söylem biçiminden bağımsız, anlamsal çekirdek” olma prensibine uygundur. Gerçekten de UMR kılavuzu, dilbilgisel kategori değiştiren yapım eki gibi eklerin çoğunun grafik üzerinde ayrı düğümler olarak gösterilmeyebileceğini, bunun yerine anlamın uygun çekirdek kavramlarla ifade edilmesi gerektiğini belirtir. Fiil çatılarında da bu yaklaşımı benimsiyoruz.

## Zaman ve Görünüş (Tense ve Aspect) İşaretleme

AMR’de fiillerin zaman bilgisi açıkça yer almazken (genelde çıkarımsaldır), UMR’de :aspect etiketi ile eylemin zaman/gerçekleşme durumu belirtilir. Türkçedeki zaman ekleri ve anlamları, UMR aspect değerlerine aşağıdaki şekilde haritalanabilir:

•	Performance (Tamamlanmış Edim) – Geçmiş zaman veya tamamlanmış eylemler için kullanılır. Türkçedeki “‑di” geçmiş zaman ekiyle yapılan fiiller genellikle bir eylemin gerçekleşip bittiğini belirtir; bu durumda :aspect Performance uygun olacaktır. Benzer şekilde gelecek zaman “‑ecek” de (olay gelecekte gerçekleşecek olsa da) gerçekleşecek bir edimi ifade ettiğinden çoğunlukla Performance olarak etiketlenebilir.

•	State (Durum) – Süreklilik arz eden durumlar ya da statik fiiller için kullanılır. Türkçede “‑dir” geniş zaman eki bazen durum ifade eder (örn. “Ali doktor‑dur”, yazı dilinde görünür, konuşmada yoktur). Bunun yanı sıra “olmak” fiiliyle belirtilen durumlar veya sıfat cümlecikleri de State olarak düşünülebilir. Örneğin “Ali yorgundu.” cümlesinde “yorgun” bir durum belirttiğinden, eğer bunu yorgun-01 gibi bir kavramla temsil ediyorsak :aspect State diyebiliriz.

•	Habitual (Alışkanlık/Geniş Zaman) – Tekrarlanan ya da genel geçer eylemler için kullanılır. Türkçede geniş zaman (“‑r” eki) bir alışkanlık veya genel bir gerçek anlatmak için kullanıldığında UMR’de Habitual ile gösterilmelidir. Örneğin “Her gün okula gider.” cümlesinde git-01 fiiline :aspect Habitual eklenir ve muhtemelen :frequency ya da benzeri bir yapı ile “her gün” belirtilir.

•	Activity (Süreçsel Eylem) – Devam eden, süreç vurgusu olan eylemler için. Türkçede şimdiki zaman “‑yor” eki ile ifade edilen eylemler genellikle bir aktivitenin sürmekte olduğunu belirtir. Bu nedenle -yor ile çekimlenmiş fiillerde :aspect Activity kullanmak uygun olur. Örneğin “Ali yemek yiyor.” için ye-01 fiiline :aspect Activity verilir; bu o anda devam eden bir eylemi gösterir.

•	Endeavor (Girişim/Çaba) – Planlanan, başlatılmış ancak tamamlanmamış veya gerçekleştirilmesine çalışılan eylemler için kullanılabilir. Türkçede gelecek zamanın bazı kullanımları veya “‑mekte” gibi yapılar, ya da “çalışmak” fiiliyle kurulan birleşik yapılar bu kategoriye girebilir. Örneğin “Ali projeyi bitirmeye çalışıyor.” cümlesinde “çalışıyor” fiili bir girişimi ifade ettiğinden :aspect Endeavor kullanılabilir; asıl bitirme eylemi henüz gerçekleşmemiştir.

UMR kılavuzunda bu beş temel görünüş değeri tanımlanmıştır ve gerektiğinde daha ince ayrımlar için alt değerlere izin veren bir kafes (lattice) yapısı mevcuttur. Standart uygulamada yukarıdaki beşli yeterli olacaktır.

Not: Türkçede hikaye geçmişi (‑miş) özel bir durumdur. “‑miş” eki, genellikle duyulan/geçmişte kalmış ama şahidin birinci elden olmadığı veya sürpriz anlamı katar. Anlam bakımından eylemin gerçekleşmiş olduğunu ifade eder (Performance), fakat konuşurun bu bilgiye dair kesinlik düzeyi düşüktür veya dolaylıdır. Bunu UMR’de ifade etmek için iki şey yapabiliriz: (1) :aspect Performance verip, (2) modal güç (modality strength) ile bir belirsizlik eklemek. UMR’de cümlenin epistemik kesinliğini belirten :modstr niteliği tam burada devreye girer. Eğer anlatıcı, olayın gerçekleştiğine dair şüpheli veya dolaylı bir konumdaysa, tam doğrulama yerine daha düşük bir kesinlik kullanılır. UMR üç derece belirler: Full (tam), Partial (kısmi) veya Neutral (belirsiz) ve bunların hem olumlu hem olumsuz halleri vardır. “‑miş” genellikle duyulan geçmiş olduğundan, anlatıcı emin olmayabilir; bu durumda “Ali gelmiş.” cümlesinin grafında gel-01 fiiline :modstr PrtAff (Partial Affırmative) eklenmesi uygun olabilir. Bu, olayın olduğu yönünde duyum var ama anlatıcı %100 emin değil demektir. Bu kullanım projeden projeye değişebilir; ancak önemli olan, ‑miş gibi modal bir ekin salt aspect ile değil, modal kesinlik ile de ilgili olduğudur.

Son olarak, şart kipi (“‑sa”/“‑se”) ile kurulan cümleler (ör. “Gelirse...”) ve istek kipi (örn. “geleydi” gibi eski dile ait) de vardır. Bunlar da birer modallik katar. Şart kipinde eylem bir koşula bağlanmıştır; UMR’de koşul cümleleri için genellikle üst bir :condition ilişkisiyle bağlanmış ayrı bir alt‑cümle grafı kurulur. İstek kipleri ise günümüz Türkçesinde nadir ve çoğunlukla edebi olduğundan, gerekirse :modstr veya :mode ile ifade edilebilir (aşağıda Mode anlatılıyor).

## Kiplik ve Modalite (Mode ve Modality)

Türkçede kip kavramı, dilek, emir, soru gibi ifadelere yansır. UMR’de :mode niteliği, cümlenin bu tür iletişim kiplerini belirtmek için kullanılır. Ayrıca modalite (kiplik) daha geniş anlamda, gereklilik, olasılık, izin gibi anlam modlarını içerir. Bunların UMR’de ifade edilmesi için hem cümle düzeyinde hem de belge düzeyinde araçlar vardır.

•	Cümle Kipleri (:mode) – Bir cümlenin soru, emir, ünlem gibi durumda olduğunu işaretlemek için kullanılır. Örneğin bir emir cümlesi için ana fiil düğümüne :mode imperative eklenir. “Kapıyı aç.” cümlesinin grafı (aç-01 :ARG1 (k / kapı) :mode imperative) şeklinde olmalıdır. Benzer şekilde soru cümlesi için :mode interrogative kullanılır: “Ali geldi mi?” cümlesi (gel-01 :ARG0 (p / person :name "Ali") :mode interrogative) gibi. Nida cümleleri veya ünlemler için :mode expressive değeri kullanılabilir (örn. “Ne güzel şeyler oldu!” cümlesi eğer bir duygu ifade ediyorsa expressive olarak işaretlenebilir).

•	Modal Fiiller ve Ekler – Türkçede gereklilik (‑meli), olasılık (‑abilir), istek (‑se veya ayrı “istemek”), zorunluluk (“zorunda olmak”) gibi modal anlamlar çeşitli biçimlerde ifade edilir. Bu anlamları UMR’de göstermek için bir modal üst fiil kullanabiliriz. İngilizcede bu “obligate-01” veya “necessary” gibi kavramlarla yapılabilir; Türkçede de belki gerek-01 fiili kullanılabilir. Örneğin “Ali okula gitmeli.” cümlesini (gerek-01 :ARG0 (p / person :name "Ali") :ARG1 (g2 / git-01 :ARG0 p :ARG1 (o / okul))) gibi iki katmanlı yapabiliriz. Alternatif olarak, daha basit bir yol, asıl fiile :modstr eklemektir. Should anlamı kesin olmayan gereklilik içerdiğinden :modstr PrtAff (kısmi olumlu) verilebilir. Ancak bu epistemik bir işaret, deontik (zorunluluk) tam karşılamayabilir. Projede netlik olması açısından, ayrı bir kavram kullanmak daha iyi izlenebilir. Bu durumda graf iki fiilli olur: Ali’nin gitmesi gerekiyor şeklinde.

•	Olasılık (‑abilir) – “‑abilir” eki, yapabilme olasılığı ya da yetenek ifade eder. Eğer yetenek anlamıysa (Ali yüzebilir = Ali can swim), bunu İngilizcedeki “can” modali gibi :mode ile değil, ayrı bir yapı ile temsil etmek gerekebilir; “can” AMR’de genelde modal olarak değil, (possible-01 ...) gibi yapılarla gösterilir. UMR’de de benzer şekilde bir mümkün olmak kavramı ya da :modstr Partial kullanımı düşünülebilir. Örneğin “Ali gidebilir.” (olasılık) cümlesini (possible-01 :ARG1 (g / git-01 :ARG0 (p / person :name "Ali"))) şeklinde yapmak olasıdır. Ya da daha basitçe git-01 düğümüne :modstr PrtAff koyulabilir (çünkü olay kesin değildir).

•	İzin/Yetki – “‑ebilmek” bazen izin bildirir (yapmasına müsaade var anlamında). Bu bağlam, olasılık ile benzer temsil edilebilir.

•	Zorunluluk – “‑mek zorunda” yapısı, zorunda‑olmak gibi bir bileşik fiil sayılıp ayrı bir kavram kullanılabilir veya :modstr FullAff ile güçlendirilmiş bir gereklilik olarak düşünülebilir. Muhtemelen en iyisi (zorunlu-01 :ARG1 (...)) gibi bir kavram eklemektir.
UMR ayrıca modpred ve quot adında iki özel ilişki tanımlar:

•	:modpred (modal predicate) bir modal fiil ile onun eylemi arasındaki ilişkiyi işaretler. Örneğin yukarıda “gerek-01” kullandığımız yapıda, gerek-01 ile git-01 arasına :modpred konulabilir (gerek-01 :modpred git-01 gibi) – gerçi Arg yapısında zaten Arg1 ile bağladık. Bu daha çok, AMR yapısından UMR’ye geçerken modallik fiillerini bağlamak için getirilmiş bir çözümdür. Eğer grafımızda zaten hiyerarşi ile bağlamışsak ayrıca koymaya gerek olmayabilir.

•	:quot ise bir söylem fiili (demek, söylemek) ile içindeki alıntı cümlesi arasındaki bağı gösterir. Örneğin “Ayşe 'geliyorum' dedi.” cümlesini (de-01 :ARG0 (p / person :name "Ayşe") :quot (g / gel-01 :ARG0 (p2 / person :ref-person 1st :ref-number Sing) :aspect Activity)) şeklinde yapabiliriz. Burada :quot ile Ayşe’nin söylediği sözün içeriğini (ikinci grafı) ana fiile bağladık.
Türkçe UMR yönergesinde, modaliteyi tutarlı temsil etmek için örnekli açıklamalar olması önemlidir. Hangi durumda ayrı bir kavram (örn. “gerek-01”, “mümkün-01”) kullanılacağı, hangi durumda sadece :modstr yeterli görüleceği örneklerle belirtilmelidir. Genel kural olarak:

•	Eğer modal anlam, cümlenin gerçekleşip gerçekleşmeme ihtimalini etkiliyorsa (epistemik), :modstr ile ifade edilebilir.

•	Eğer modal anlam, bir gereklilik veya izin gibi dışsal bir koşulu ifade ediyorsa (deontik), ayrı bir kavramla (örn. zorunluluk, izin fiilleri) ve :modpred ilişkisiyle ifade etmek gerekebilir.

## Niceliksel İfadeler ve Kapsam

Türkçe cümlelerde “her, bazı, hiçbir, çoğu” gibi nicelik bildiriciler ve “‑den fazla, ‑den az” gibi yapılar bulunur. UMR’de niceliksel ifadeleri temsil ederken:

•	Sayılar doğrudan :quant değeri olarak ilgili isme bağlanır. Örneğin “iki kedi” için (k / kedi :quant 2).

•	“birkaç, birçok, az, çok” gibi belirsiz nicelikler de :quant ile verilebilir, ancak bu kelimelerin tam karşılığı sayı olmadığı için bunlar kavram olarak gösterilebilir. Örneğin “birkaç öğrenci” ifadesini (ö / öğrenci :quant (b / birkaç)) şeklinde yapabiliriz; burada birkaç ayrı bir kavram (sıfat) oldu.

•	“her” ve “hiçbir” gibi dağıtıcı veya tümleyici nicelikler de benzer biçimde kavram olarak (her belki all veya each kavramına karşı gelir) kullanılabilir. Örneğin “Her öğrenci” için (ö / öğrenci :quant (h / her)) yapılabilir. Alternatif olarak Quantifier Scope (Niceleyici Kapsamı) özelliğini kullanarak daha üst düzeyde bir temsil yapılabilir. Ancak genellikle bu düzey ayrıntıya gerek kalmaz.

Eğer bir cümlede birden fazla nicelik varsa ve bunların farklı kapsam yorumları mümkünse (örneğin “Her öğrenci bir kitap okudu.” cümlesinde dağıtıcı mı yoksa toplam mı okuma olduğu), UMR’de scope kavramı eklenerek hangi niceliğin diğerine göre geniş kapsamlı olduğu işaretlenebilir. Bu ileri seviye bir anotasyon olup karışık durumlarda uygulanır. Kural olarak, bir cümlenin yüzeysel okunuşu ile aynı olan kapsam ilişkilerini ayrıca işaretlemeye gerek yoktur; ancak standart dışında bir okuma söz konusuysa scope anotasyonu yapılır.

“tüm, hepsi” gibi ifadeler de gene :quant (tüm) veya ayrı bir yapıda ele alınabilir. Belirsiz durumlarda, örneğin “Onlar iki kitap okudu” (her biri mi iki kitap toplamda mı?), kapsam belirtmek gerekebilir. Benzer şekilde, karmaşık cümlelerde niceleyicilerin kapsamı yoruma açık olabilir; bu gibi durumlarda graf yapısına bir scope düğümü eklenerek belirsizlik giderilir.

UMR’de kapsam anotasyonu, graf yapısına (s / scope ... ) şeklinde bir düğüm ekleyerek nicelik ve negasyonların göreli sırasını belirtmeyi içerir. Bu oldukça teknik bir ayrıntıdır; başlangıç seviye kılavuzunda çok derine girmeden, yalnızca ihtiyaç duyulursa kullanılacağını not etmek yeterli olabilir.

## Özel Adlar ve Ad Tamlamaları

Özel isimlerin etiketlenmesini yukarıda ele aldık. Burada, ad tamlamaları ve belirtili/belirtisiz tamlamalar için birkaç kural belirtelim:

•	Belirtili Tamlamalar (İyelik eki olan): “Ali’nin kitabı” gibi. Bu yapıları genelde bir sahiplik ilişkisiyle temsil edeceğiz (örn. :poss). Üstte verdik: (k / kitap :poss (p / person :name "Ali")). Eğer tamlama soyut bir sahiplik değil de bir parça‑bütün ilişkisi ise :part-of veya tersine :part kullanılabilir (örn. “arabanın motoru” için (m / motor :part-of (a / araba))). Dolayısıyla tamlamanın anlamına göre uygun ilişki seçilmeli:

•	Sahiplik ⇒ :poss

•	Parçalık ⇒ :part-of veya tersine :part

•	Konum tamlaması ⇒ belki :location (Türkiye'nin başkenti için (b / başkent :location-of (t / Türkiye))).

•	Özellik bildiriyorsa (sıfat gibi) ⇒ :mod veya ilgili bir rol (örn. “çocuk kitabı” aslında çocuklar için kitap demek; yani amaç belirtiyor, belki :purpose ile yapılabilir (k / kitap :purpose (ç / çocuk)) – bu yorum meselesi).

•	Belirtisiz Tamlamalar: “köpek balığı”, “demir kapı” gibi “of” kullanılmayan birleşikler. Bunlarda genelde ikinci isim ana kavramdır, ilk isim onu niteleyen bir rol üstlenir. AMR’de çoğunlukla :mod etiketi bu iş için kullanılır. “demir kapı” için (k / kapı :mod (d / demir)), “köpek balığı” için (b / balık :mod (k / köpek)) yapılabilir. Burada tabii “köpek balığı” aslında “shark” anlamında sabit bir birleşikse, belki doğrudan köpekbalığı tek kavramı kullanılabilir. Bu, proje kararına bağlı. Eğer kelime birleşik yazılıyorsa (örn. “asma kilit” ayrı ama “başkent” bitişik yazılır), genelde bitişik olanlar tek kavram, ayrı yazılanlar mod ilişkisiyle yapılabilir. Ancak bu kural dilbilgisel değil yazımsal; anlamsal tutarlılık için listelemek iyi olur.

•	Sıfat Tamlamaları: “büyük ev”, “kırmızı araba” gibi. Bunlarda da sıfat kavramı ayrı bir düğüm olarak :mod şeklinde bağlanır: (e / ev :mod (b / büyük)). Eğer sıfatın derecesi varsa (örn. “çok büyük”), :degree özelliği kullanılabilir (büyük :degree intensifier gibi) veya çok ayrı bir kavram olup :mod ile sıfata bağlanabilir. UMR, derece belirteçleri için intensifier/downtoner nitelikleri tanımlar. “en büyük” için belki büyük :degree superlative gibi bir şey tanımlanabilir (kılavuzda net değilse eklenebilir).

•	İsim-Fiil ve Sıfat-Fiiller: Türkçede fiilden türeyip isim veya sıfat gibi kullanılan yapılar (ör. “koşu”, “yazan kişi”). Bunlar anlamsal olarak fiil içerir. “koşu” (koşma eylemi) bir event nominalization örneğidir. AMR’de bunları genelde fiil kavramıyla temsil etmek tercih edilir (çünkü fiil anlamı içerir). UMR’de de benzer yaklaşım önerilir. Örneğin “Ali’nin koşusu hızlıydı.” cümlesinde “Ali koştu ve bu koşu hızlıydı” anlamı var. Grafı (koş-01 :ARG0 (p / person :name "Ali") :manner (hızlı)) yaparsak, hem koşma eylemini, hem onun hızlı gerçekleştiğini, hem de Ali tarafından yapıldığını anlatmış oluruz. Orijinal cümle isim tamlaması şeklinde olsa da, UMR’de fiil kavramıyla ifade edildi. Bu sayede dilsel biçimden bağımsız anlam yakalanmış oldu. Benzer şekilde sıfat-fiil (ortaç) yapıları da uygun şekilde alt cümlecik olarak temsil edilmelidir. Örneğin “[Ali’nin yazdığı] mektup” tamlamasında aslında “Ali mektup yazdı” anlamlı bir alt cümle var. Grafı (m / mektup :ARG1-of (yaz-01 :ARG0 (p / person :name "Ali"))) biçiminde kurabiliriz. Yani yaz-01 fiilini kullanıp, onun Arg0ını Ali, Arg1ini mektup yaparız; sonra mektup düğümünü ana isim olarak tutar, fiili onun özelliği olarak Arg1-of ile bağlarız (veya tersine :mod da diyebilirdik ama Arg1-of daha açıklayıcı). Bu gösterim, relative clause (ilgi cümleciği) olarak AMR/UMR’de tercih edilir.

## Deyimsel ve Mecazi İfadeler

Her dilde olduğu gibi, Türkçede de deyimler ve mecazlar bulunmaktadır. Bu tür ifadelerde yüzeysel kelime anlamları yerine asıl kastedilen mecaz anlamı graf üzerine yansıtmayı tercih ederiz. UMR projesi, idiomatic phrases (deyimsel ifadeler) konusunu hem AMR hem UMR için zorlu bir alan olarak tanımlar. Anlamı bütünüyle farklıysa, mümkün olduğunca benzer bir hedef dil kavramıyla ifade etmeye çalışın:

•	Eğer Türkçedeki deyimin başka bir dilde doğrudan karşılığı yoksa, kendi dilimizdeki anlamını açıkça yazabiliriz. Örneğin “kafayı yemek” deyiminin anlamı “aklını kaçırmak/delirmek” şeklindedir. Bunu UMR grafında (deli-01 :ARG0 (p / person)) gibi bir kavramla verebiliriz; gerekirse özel bir işaretleme eklemeyiz çünkü artık literal “kafa” ve “yemek” kavramları grafımızda yok, yerine anlamı koyduk.

•	Bazı deyimler ise aslında bileşik fiil gibidir (“fırsatı kaçırmamak”, “göz ardı etmek”). Bunlar genelde bir fiil kavramıyla temsil edilebilir (örneğin “göz ardı etmek” = ignore-01 olarak tek kavram). Eğer Turkish PropBank’te bu şekilde tanımlanmışsa kullanın, yoksa siz benzer bir etiket seçin ve tutarlı uygulayın.

•	Mecazi kullanımda, eğer ifade anlaşılır bir benzetmeyse ve anlamı da kelimelerden çıkarılabiliyorsa belki literal temsil de düşünülebilir ama genelde anlamsal doğruluk önceliklidir. Örneğin “kalbini kırmak” (incitmek) için (incit-01 :ARG0 ... :ARG1 ...) kullanmak tercih edilir; literal “kalp” ve “kırmak” kullanılmaz.

Kısacası, deyimleri anlam odaklı çözerek grafı oluşturun. Bu, ileride model eğitimi veya anlambilimsel arama yapılırken tutarlılık sağlayacaktır. UMR kılavuzunun da belirttiği gibi, aşırı dil‑özgü kavramlara bel bağlamamak, mümkün mertebe evrensel kavram envanteri içinden seçim yapmak önemlidir. İngilizceye dayalı kavramlar yerine Türkçenin kendi söz varlığından veya BabelNet gibi çok dilli sözlüklerden gelen kavramlar tercih edilmelidir.

## Cümleler Arası Bağlantılar (Belge Düzeyi)

UMR’nin güçlü yönlerinden biri, birden fazla cümlenin anlamını tek bir birleşik yapı halinde ifade edebilmesidir. Bu, özellikle çözümleme yapılan metin birden fazla cümleden oluşuyorsa önem kazanır. Türkçe UMR etiketlemesinde belge düzeyi anotasyonlar için şu prensipler önerilir:

•	Her cümle kendi kök grafına sahip olur ve genellikle bir sentence düğümü ile işaretlenebilir. Örneğin, bir metindeki ilk cümle için (s1/ sentence ...), ikinci cümle için (s2/ sentence ...) gibi üst düğümler kullanılabilir. Bu düğümlerin altında o cümlenin asıl AMR/UMR grafı gelir. Bu yapıyı kullanmak isteğe bağlıdır ancak cümleler arası ilişkileri bağlamak için rahatlık sağlar.

•	Özdeş varlıkların işaretlenmesi (Coreference): Eğer bir varlık (kişi, nesne vb.) birden fazla cümlede geçiyorsa ve aynı gerçek dünyadaki kişiyi kastediyorsa, bunları UMR grafiklerinde bağlamak mümkündür. Bunun için bir cümledeki varlık düğümüne, başka bir cümledeki varlığa referans veren bir :same-entity ilişkisi konulur. Örneğin:

(s1/ sentence
     :ARG0 (p / person :name "Ali") ...)
(s2/ sentence
     :ARG0 (p2 / person :pron "o") ...)
:coref (p2 :same-entity p)

Bu yapı, ikinci cümledeki “o” zamirinin birinci cümledeki “Ali” ile aynı varlık olduğunu belirtir. UMR’de bu coreference bağı genellikle en tepeye, sentence düğümlerinin dışına yazılır. Bu sayede, cümleler arası bağlar grafın bir parçası olur.

•	Zamansal İlişkiler: Farklı cümlelerdeki olayların zaman ilişkilerini belirtmek için :temporal ilişkisi belge düzeyinde de kullanılabilir. UMR’de yaygın olarak, Document Creation Time (DCT, belgenin yazıldığı an) referans alınarak olayların ondan önce/sonra olduğu veya birbirleriyle örtüştüğü ifade edilir. Örneğin birinci cümledeki bir olay ikinci cümledekinden önce gerçekleştiyse, :temporal (s1/ sentence :before s2/ sentence) gibi bir gösterim yapılabilir (tam söz dizimi projeye göre şekillenir). UMR’deki örneklerde her cümlenin alt olayları için indexli etiketler kullanılıp sonra üstte :temporal ((s1e1 :before s2e1)) gibi yapılar görülmektedir.

•	Modal İlişkiler (Kaynak Gösterimi): Metinde bir cümle bir iddiayı, diğer cümle onu aktaran kişiyi içeriyorsa, bunun gibi durumlar belge seviyesinde modal ilişki olarak gösterilebilir. Örneğin bir cümlede yazarın bir olaya kesin olarak bildiği, diğerinde bir karakterin söylediği bir bilgi varsa, conceiver (algılayan) farklı kişilerdir. UMR, belge düzeyinde AUTH (author) gibi belirteçlerle kimin perspektifi olduğunu işaretleyebilir. Bu ileri düzey bir özellik olup gerekli oldukça kullanılabilir.

Tutarlılık: Belge düzeyinde bağlantılar eklenirken, cümlelerin kendi iç grafik yapıları değişmez. Yani önce cümlelerin UMR grafikleri hazırlanır, sonra aralarına yukarıdan bağlantılar eklenir. Bu modülerliği korur.

Türkçe için, özellikle özne tekrarları (“Ali ... O ...” şeklinde) ve zaman bağlaçları (örneğin “önce”, “sonra”, “iken”) önemli belge düzeyi ilişkiler doğurabilir. Kılavuzda bu türden en az bir örnek bulunması öğretici olacaktır.

## Örnek Anotasyonlar

Aşağıda, Türkçe cümleler için UMR etiketleme kurallarını uygulayan örnekler verilmiştir. Her örnekte önce cümle, ardından UMR graf temsili ve kısa açıklaması sunulmaktadır:

## Örnek 1: Ali okula gitti.

Bu cümlede özne açıktır (“Ali”), fiil geçmiş zamanlıdır (“gitti”), nesne “okul”dur.

```lisp
(g / git-01
   :ARG0 (p / person :name "Ali")
   :ARG1 (o / okul)
   :aspect Performance
   :modstr FullAff)
```


Açıklama: git-01 kavramı Türkçe PropBank’ten alınmış “gitmek” eylemini temsil ediyor. :ARG0 pozisyonunda Ali’yi bir person düğümüyle belirtip ismini verdik. :ARG1 olarak “okul” doğrudan kavram olarak eklendi. Fiilin geçmiş zaman olması, gerçekleşmiş bir eylem olduğunu gösterdiğinden :aspect Performance etiketi kullanıldı. Cümle düz bir bildirim cümlesi olduğu için modal kesinlik FullAff (tam olumlu) kabul edilmiştir. Bu grafik, “Ali okula gitti” anlamını tam olarak yakalar.

## Örnek 2: Kapı kapandı.

Bu cümlede edilgen yapıda bir fiil içerir, özne (fail) belirtilmemiştir.
```lisp
(k2 / kapı
      :ARG1-of (kapan-01
                  :aspect Performance
                  :modstr FullAff))
```
Açıklama: Burada kapan-01 fiil kavramını kullandık (PropBank’te varsa veya kapa-01 + pasif diyerek belirledik). :ARG1-of yapısı ile kapı nesnesini fiile bağlıyoruz; yani fiilin Arg1’inin kapı olduğunu ifade ediyoruz. Arg0 (kapatan kişi) yoktur, çünkü cümlede belirtilmemiş. Aspect yine Performance (olay gerçekleşmiş, kapı kapanmış) ve modstr FullAff (anlatıcı bu olayın olduğunu kesin biçimde söylüyor). Pasif yapı ekstra bir şeye ihtiyaç duymadan bu şekilde temsil edildi.

## Örnek 3: Ben yarın geliyorum.

Bu cümlede 1. tekil şahıs zamir özne düşmüştür (fiil ekiyle anlaşılıyor), fiil şimdiki zamandadır, bir zaman zarfı vardır.
```lisp
(g / gel-01
     :ARG0 (p / person :ref-person 1st :ref-number Singular)
     :temporal (t / yarın)
     :aspect Activity
     :modstr FullAff)
```
Açıklama: Özne “ben” cümlede yok, fakat grafımızda (p / person ...) ile birinci tekil kişi olarak eklendi. Zaman belirtecini “yarın” kavramı ile :temporal ilişkisi altında belirttik. Fiil şimdiki zaman devam ediyor (yarın gerçekleşecek olmasına rağmen konuşma anında planlanmış bir yakın gelecek – bunu genelde progressive/Activity sayabiliriz). Bu yüzden :aspect Activity dedik. Anlatım düz bir ifade, FullAff. Sonuçta graf “(Ben) yarın geliyorum” anlamını içeriyor.

## Örnek 4: Ali, Ayşe’nin gelmesini bekliyor.

Bu cümlede bir yan cümlecik var (“Ayşe’nin gelmesi”), ana cümle fiili beklemek, şimdiki zaman.
```lisp
(b / bekle-01
     :ARG0 (p / person :name "Ali")
     :ARG1 (g / gel-01
              :ARG0 (p2 / person :name "Ayşe")
              :ARG1 p2   ;; Ayşe'nin gelmesi, kendisi geliyor (Arg1 yok, intransitive sayılır)
              :aspect Performance
              :modstr FullAff)
     :aspect Activity
     :modstr FullAff)
```
Açıklama: bekle-01 ana fiil, Ali onun öznesi. Beklenen şey Arg1 olarak eklendi: bir gel-01 eylem düğümü. Bu düğüm Ayşe’nin gelişini temsil ediyor. Ayşe’yi orada :ARG0 yaptık. gel-01 intransitive (sadece gelen var, Arg1 kullanmadık veya kendisine Arg1 verdik p2 olarak; burada farklı gösterim tercihine bağlı). Ayşe’nin gelme eylemi gerçekleşecek (Ali bekliyor, henüz olmadı ama beklenen bir olay), belki Performance dedik ancak henüz gerçekleşmemiş olabilir – burada bir ihtilaf var. Alternatif olarak Ayşe’nin gelişi bir Endeavor ya da belki :modstr belirsiz olarak düşünülebilir. Basit yaklaşım: Ali bekliyor, Ayşe gelecek diye düşünüyor; şimdilik FullAff Performance dedik. Ana fiil bekliyor ise halen sürüyor, :aspect Activity verdik. Bu grafik, iç içe yan cümleyi gösteren bir yapıdır. Bekleme fiili ile gelme fiili arasında :ARG1 ilişkisi kuruldu, böylece “Ali [Ayşe’nin gelmesini] bekliyor” yapısı anlaşılır oldu.

## Örnek 5: Eğer yağmur yağarsa maç iptal olacak.

Koşullu bir cümle örneği; iki yargı içeriyor.
```lisp
(s1/ sentence
      :condition (y / yağ-01
                    :ARG0 (y2 / yağmur)
                    :aspect Performance
                    :modstr FullAff)
      :ARG1 (i / iptal-01
               :ARG1 (m / maç)
               :aspect Performance
               :modstr FullAff)
      :mode declarative)
```
Açıklama: Bu biraz şematik bir gösterim. Koşul yapısı olduğu için bir :condition ilişkisi kullandık. Ana cümlemiz “maç iptal olacak” – bunu iptal-01 (fiil veya sıfat yapabiliriz; fiil kabul ettik) ile maç Arg1 olacak şekilde gösterdik. Koşul kısmı “yağmur yağarsa” – yağ-01 fiili (yağmurun yağması) ve yağmur Arg0 olarak eklendi. Bu alt cümleyi :condition ile ana cümleye bağladık. Zaman açısından iptal olacak = gelecekte, ama :aspect Performance dedik (gerçekleşecek bir eylem olarak). Yağmur yağarsa kısmı da gerçekleşirse anlamında; koşa bağlı, ama kendisi bir olay; Performance dedik. İhtiyaca göre belki :modstr Neutral (belirsiz) denebilirdi koşullu olduğu için. Örnek amaçlı böyle gösterdik. Bu yapı, tek bir sentence düğümü altında koşul ve ana sonucu bağlamış oldu. Alternatif olarak belgesel düzeyde iki sentence ayrı yazılıp temporal/modal ilişki de kurulabilirdi; ancak genelde tek cümle içinde koşul bu şekilde gösterilir.

## Örnek 6: “Geliyorum” dedi Ali.

Doğrudan konuşma örneği; alıntılı ifade.
```lisp
(say / de-01
     :ARG0 (p / person :name "Ali")
     :ARG1 (g / gel-01
              :ARG0 (p2 / person :ref-person 1st :ref-number Sing)
              :aspect Activity
              :modstr FullAff)
     :mode declarative
     :quot g)
```
Açıklama: Ali’nin söylediği cümleyi, ayrı bir alt graf (g / gel-01 ...) olarak Arg1 konumunda verdik. Burada :ARG0 p2 = birinci tekil kişi (konuşanın perspektifinde “ben” demek, ancak o Ali olduğundan aslında Ali kendini kastediyor – bu karışık bir nokta; ancak biz sadece alıntıyı doğrudan temsil ediyoruz). :quot ilişkisini kullanarak bu alt grafı de-01 fiiline bağladık. Bu, bunun bir alıntı olduğunu gösterir. Sonuçta “Ali 'Geliyorum' dedi” anlamı yakalanmış oldu.

Bu örnekler, Türkçe UMR etiketlemesinde sık karşılaşılacak durumlar için kılavuz niteliğinde hazırlanmıştır. Gerçek bir UMR‑Turkish kılavuzu, bunlara ek olarak daha karmaşık cümle tipleri, farklı fiil çatıları, deyimler listesi, kapsamlı bir ilişki ve rol envanteri gibi bölümler de içermelidir. Burada sunulan şablon başlangıç noktası olarak düşünülmüştür. İleride GitHub üzerinde paylaşılacak tam kılavuz, bu şablonu genişleterek daha fazla örnek ve ayrıntıyla Türkçe UMR Etiketleme Rehberini tamamlayacaktır. Böylece Türkçe cümlelerin anlamsal temsili konusunda tutarlı ve anlaşılır bir standart oluşturmak mümkün olacaktır.

## Kaynaklar

Shira Wein,  Julia Bonn. "Comparing UMRandCross-lingual Adaptations of AMR".

Oral, Kadriye Elif. "Abstract meaning representation of Turkish".

Gerekli Kural Yapıları için Github linki: "https://github.com/umr4nlp"
________________________________________


