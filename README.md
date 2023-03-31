## LİNUX DOSYA SİSTEMİ HİYERARŞİSİ

Linux’un Windows’dan farklı olan dosya hiyerarşi sistemini kavramak ve ileride ele alacağımız dosya-dizin işlemleri konularında zorluk çekmemek adına bu kısımda _“Linux dosya sistemi hiyerarşisi”_ konusunu ele alacağız.

Linux sistemlerinde de aynı şekilde sınıflandırma yapılarak dosyaların sıraya koyulmasına, aslında bir ağaç misali oluşan dosya sistemlerine genel olarak _“Linux dosya sistemi hiyerarşisi”_ deniyor.

Genellikle bütün dağıtımlarda aynı hiyerarşik düzen vardır.(Genellikle diyoruz çünkü küçük farkların dışında tüm dağıtımlar aynı hiyerarşik yapıya sahiptir.)

Linux _"Tekil Hiyerarşik Klasör Yapısı"'nı_ benimsiyor. Yani bu da şu demek oluyor; her şey / (slash) simgesiyle ifade edilen root klasöründen başlar, aşağıya doğru iner. Root kelimesi de Türkçe’de Kök anlamına geliyor.

Linux, / (root) klasöründen başlayarak, boot işlemindeki önem sırasına göre klasörleri ilgili konumlara yerleştirir. Bu yerleştirme işleminde, yani klasörler arası geçişlerde klasörler arasını ayırmak için /(slash) işareti kullanılır. Herhangi bir dizin ya da dosyanın sistemdeki adresi önce kök dizinden başlar sonra o dosya ya da dizine ulaşmak için geçilmesi gereken dizinler arasına yine / yazılarak elde edilir.

Ayrıca şunu da belirtelim, Linux küçük büyük harf duyarlılığına sahiptir. Yani Linux'ta DOSYA_ADI, Dosya_Adı, dosya_adı, DoSyA_aDı.. vb. gibi isimlendirilmiş dosyaların hepsi ayrı/farklı bir dosya olarak tanınır. Windows'ta ise aynı isimli dosyalar, küçük büyük harf ayrımı gözetilmeksizin aynı olarak tanınır.

Windows işletim sistemine bir program eklediğimizde programın dosyaları Program Files(Program Dosyaları) dizini içerisine programın kendi adındaki bir klasöre eklenir.(Örneğin C:\Program Files\program_adı şeklinde.) Programın dosyaları tek bir dosya içerisindedir yani.

Özetle Linux sisteminde her şey bir dosya(root-kök dosyası(/)) içerisinde yer alır. Ve bu dosya sistemi hiyerarşik bir yapıda bulunur. Tüm bu tek kök dosya sistemi ve hiyerarşik yapılanmanın amacı çok kullanıcılı ve dağıtık bir sistemi güvenli ve kolay bir şekilde kurup yönetebilmektir. Örneğin x_bilgisayarı'na /bin dizini bağlanır, bir diğer bilgisayara /var dizini içerisindeki e-posta sunucusunun dosyalarının olduğu dizin, bir diğerine de /home dizini bağlanabilir.

Bu sayede fiziksel olarak pek çok bilgisayara dağılmış olan bir sunucu tek bir kök dosya sisteminden, sanki tek bir bilgisayarmış gibi yönetilerek kullanılabilir. Bu sayede hem iş yükü dağılımı yapılarak sistem performansı arttırılmış olur hem de yetkilendirme ve yönetim kısıtlamaları dahilinde sistemin ayrı ayrı parçalara dağılımı ile sisteme ekstra güvenlik önlemi katılmış olunur. Biraz daha net anlamak adına aşağıdaki görseli inceleyebilirsiniz.

Şimdi çoklu kullanıcılar için neden güvenli olduğunu daha iyi anladık ama ben sadece kişisel bilgisayarımdan kullanacağım bu dosya sistemi benim için gereksiz." diyebilirsiniz. Ancak bu dosya sistemi tekil kullanıcılar için de sağladığı güvenlik özellikleri nedeniyle gerekli bir sistemdir.

Daha iyi anlamak için benzer bir duruma masaüstü kullanıcıları için örnek verecek olursam benim yetkim olmadığı bir kullanıcıda değişiklik yapamadığımı göreceğim rootta ise yetkimi yükselterek istediğim değişikliği yapabileceğimi göreceğim.

Artık kısaca Linux dosya sisteminin neden bu şekilde olduğunu ve sağladığı avantajları anladıysak, gelin bu hiyerarşik yapıdaki dosyalara ve işlevlerine daha da yakından bakalım.

Vereceğim bilgiler ezberlenmesi gerekmiyor ama bunları anladığınızda neyin nerde olduğunu kavramış olacaksınız linux kullanırken işinize yarayacak.

### /bin

İşletim sisteminizi kullanmak için gereken birçok komut /bin klasörü altındadır. cat, mkdir, cp, ls, mv, rm vb. temel komutların hepsi buradadır. Sistem boot ettiğinde, ilk olarak /bin klasörü çalışır hâle getirilir. Sistemde ne kadar ciddi bir sorun olursa olsun /bin klasöründeki komutlar çalışmaya devam eder. Bu sayede sisteminizde bir sorun meydana geldiğinde /bin klasörü altındaki temel komutları kullanarak sistemi onarabiliriz.

### /boot

Boot, işletim sisteminin yüklenme evresidir. /boot klasörü, boot, başlatma işlemi için gerekli olan tüm dosyaları içerir (çekirdek görüntüsü, sistem haritası, önyükleyici yapılandırması gibi). Bilgisayarın başlangıç (boot) aşamasında gerekmeyen ayar ve yapılandırma dosyaları burada bulunmaz; başka klasörlerden gerektiği zamanlarda yüklenir.

### /dev

Device kısaltması. Linux'ta her şey bir dosyadır; donanım aygıtları da öyle. USB girişleri, seri ve paralel portlar, depolama ortamları, CD-ROM'lar vb... Bütün aygıtlar /dev klasörü altında tutulan dosyalardan ibarettir. Örneğin /dev altında bulunan sda1 dosyası, sabit diskinizi temsil eder. Ya da /dev/dsp, ses aygıtınızdır. Bunları programlar vasıtasıyla kullanırız; ancak bu dosyalar üzerinden doğrudan müdahale etmek de mümkündür.

### /etc

Sisteme dair bütün ayarları ve bilgisayara özel birçok yapılandırma bilgisini içerir. Biraz linux üzerinden ayrıntısına bakalım

Köke geldikten sonra cd diyip taba basıyorum gördüğünüz gibi dosyaları görebiliyorum

Shadow dosyası var ona bakalım

Cd / , cd /etc , sudo cat shadow diyorum

Burada sistemdeki kullanıcıların hashlenmiş parolaları bulunmakta. Hash algoritmalarla encrypte edilmiş demek. Yani okunamaz halde şu an. Buradaki hashlenmiş detayların ne anlama geldiğini ilerde göreceğiz.

Cat passwd dediğimde gördüğünüz gibi kullanıcı adları yetkileri vs görebiliyorum

### /home

home klasörü kullanıcıların kalesi olarak tabir edilir. home klasörü içerisinde her kullanıcının kendi adında bir alt klasörü bulunur. (örneğin /home/ahmet , /home/ayşe gibi). Kullanıcıların kişisel verileri, kullandığı programlarda yaptığı ayar değişiklikleri, yapılandırmaları burada tutulmaktadır. Ayrıca kullanıcılar /home dizinini elbette belge, müzik, resim vb. dosyaları düzenli, tertipli bir şekilde depolamak amacıyla da kullanabilirler.

### /initrd

initrd, "initial ramdisk" kısaltmasıdır. Anlamı, yaklaşık olarak "Başlangıç Bellek Diski" şeklinde ifade edilebilir. Boot aşamasında ilk önce çekirdek (kernel) yüklenir. Bundan sonra bilgisayarınızın belleğinde bir Bellek Diski oluşturulur. Oluşturulan Bellek Disk üzerinde / (root) yansısı açılır ve kök dizin olarak monte edilir. /initrd bu işlemlerin yapılması ve Linux'un yüklenmesi için gereklidir.

### /lib

Çekirdek (Kernel) modülleri ve paylaşılan kütüphane dosyaları bu klasörde bulunur. Kütüphane dosyaları, sistemi başlatmak ve /bin ile /sbin içerisindeki komutları çalıştırmak için gereklidir. Paylaşılan kütüphane dosyalarını, Windows'ta DLL ile eş tutabiliriz. Linux'ta kütüphane dosyalarının sonu ".so" ile biter.

### /lib64 /lib32

Halen 32 bit ve 64 bit sistemler arasında geçiş yapıyoruz. Bu nedenle, kütüphane dosyalarının derleme süresi boyunca kullanılan kayıt boyutunu netleştiren /lib32 ve /lib64 adlı dizinlerle karşılaşabilirsiniz. Yani bu sayede 64 bitlik bir bilgisayar, eski uygulamalara uyumluluk için bazı 32 bitlik ikili dosyalara ve kütüphanelere sahip olabilir.

### /lost+found

İngilizce bir terim olan “Lost and Found” kayıp eşya bürosu demektir. /lost+found klasörü de tam olarak bu işlevi görmektedir. Bazen sisteminizde herhangi bir problem olur; örneğin bilgisayarı resetlerseniz, elektrik gider sonrasında bilgisayarı yeniden başlatırsınız. Bu gibi durumlarda Linux'ta fsck (File System Check) komutu devreye sokulur. Düzeltilemeyen bir sorun varsa, bağlantıları kopmuş kayıp dosyalar ortaya çıkmışsa, bunlar /lost+found altına atılır. Kısaca özetlersek; kötü bir sistem kapanmasından sonra, olması gereken bazı dosyaları bulamıyorsanız, kayıp eşya bürosuna bakmanızda yarar var.

### /media

Kaldırılabilir aygıtların (USB bellek, SD kart, CD vb.) ve sistem başlangıcında bağlanmayan sabit disk bölümlerinin bağlanma noktasıdır. Söz konusu depolama ortamları sisteme bağlanmamış iken dizin içeriği boş görünür.

### /mnt

İşletim sisteminin kurulu olduğu disk bölümü hariç olmak üzere sistem başlangıcında bağlanan sabit disk bölümleri ve donanım aygıtlarının bağlanma noktasıdır. (İşletim sisteminin kurulu olduğu disk bölümünün içeriği ise doğrudan / (kök dizin) altında bulunur.)

Bağlama(mount) işlemi, bir disk bölümünün sisteme bağlanarak kullanıma hazır hâle gelmesi demektir. Nereye bağladığınız sizin tercihinizdir, değiştirmeniz mümkündür. Yani bir diski, /media veya /mnt klasörüne ya da bir başka yere bağlamanız fark etmeyecektir. /media ve /mnt sadece genel kabul görmüş bağlantı noktalarıdır.

### /opt

İşletim sisteminden bağımsız, sistem için zorunlu olmayan 3. parti kullanıcı programları bu dizinde bulunur. Örneğin; Google Earth programını indirip kurmak istediğinizde, varsayılan olarak kurulacağı nokta, /opt/google-earth adresidir.

Elbette üçüncü parti bir programı kurarken bu kurulum konumunu değiştirebilir, size uygun gelen bir başka konuma yükleyebilirsiniz. Ancak daha önce de bahsettiğimiz gibi bazı şeyler genel kabule dayanır.

### /proc

Süreçler, sistem belleği, bağlı aygıtlar, donanım yapılandırmalarıyla ilgili bilgileri içeren özel bir “sanal” dosya sistemidir. Bildiğimiz anlamda fiziksel dosyalar bulundurmaz; sistem durumuna dair bilgi içeren sanal dosyaları vardır. Bir bilgi alma merkezi olarak görülebilir, birçok uygulama buradaki bilgilerden yararlanmaktadır. Örneğin cat /proc/swaps yazarak sisteminizdeki takas dosyalarına dair bilgi alabilir ya da cat /proc/cpuinfo komutuyla işlemcinizin özelliklerini görebilirsiniz.

/proc klasörü içerisindeki dosyalar, sadece sistem durumunu görüntülemek için kullanılmaz, gerektiğinde sistemde ayarlama yapmak için de kullanılabilir.

### /root

Linux/Unix sistemlerde, işletim sistemine her türlü müdahalede bulunabilme yetkisine sahip, "root" adıyla tanımlanmış, süper yetkili özel bir kullanıcı hesabı vardır. /root dizini, bu özel kullanıcı hesabının ev dizinidir. Daha iyi anlamak adına örneğin; "burak" isimli kullanıcı hesabının ev dizini /home/burak şeklindeyken "root" kullanıcısının ev dizini /root dizini şeklindedir. Root kullanıcısına daha önce de belirttiğimiz şekilde "kök kullanıcı" da denilir.

Kullanıcıların, sistemi root hesabıyla açma ihtiyacı bulunmaması nedeniyle ve ayrıca sistemi root olarak açmanın güvenlik zaafiyetine yol açabilecek olması nedeniyle pek çok Linux dağıtımında root hesabıyla sisteme giriş yapılması, öntanımlı olarak engellemiştir. Ancak istisnaya dahil olan "Kali Linux" dağıtımı penetrasyon testleri ve bunun gibi siber güvenlik işlemleri için oluşturulduğundan kullanıcılar için kolaylık olması için tam yetkili olarak çalışır.

### /run

Son önyüklemeden bu yana çalışan sistemle ilgili bilgileri tutar. Tutulan bilgilere örnek vermek gerekirse şu anda oturum açmış kullanıcılar, sisteme bağlanan aygıtlar, ağ ile bağlantı(network) değişimleri ve bunun gibi bilgileri tutar.

### /sbin

Linux'ta normal kullanıcının kullanabileceği komutlarla, kök kullanıcının (root) kullanabileceği komutlar ayrılmıştır. root tarafından kullanılacak bakım ve yönetim için kullanılan önemli programlar, /sbin altında tutulur. Daha az öneme sahip yönetim komutlarıysa, /usr/sbin klasöründedir. Eğer yerelde, yani kullandığınız makineye özgü kök kullanıcı (root) komutları bulunuyorsa, bunları da /usr/local/sbin altında bulabilirsiniz.

### /usr

Unix ilk çıktığında, kullanıcılara ait ev klasörleri, /usr altında tutulurdu. Örneğin; "burak" isimli bir kullanıcının ev klasörü /usr/burak şeklindeydi. Bu yöntem zamanla değişti ve /home klasörü doğmuş oldu. /usr klasörü hâlâ çok önemli bir yapıdır ve işletim sisteminizde kullandığınız her şeyle ilişkisi bulunur.

Kurduğunuz pek çok program /usr içine kurulur. Her ne kadar Linux'ta kurulan bir programa ait tüm dosyalar usr dizini içine atılmıyor olsa da usr dizini Windows'taki Program Files klasörü ile benzer görev görmektedir. /opt adresi işletim sistemi dışında gelen 3.parti programlar içindir. Fakat işletim sistemi aracılığıyla ya da paket yönetim sistemlerini kullanarak yüklediğiniz her şey /usr altına aktarılır. Aynı zamanda yüklediğiniz programların çalışmak için ihtiyaç duyacağı kütüphane dosyaları, /usr/lib altındadır.

/usr, daha geniş bir tanımla; tüm kullanıcılarca paylaşılan verileri (programlar, komutlar, kütüphaneler, dokümanlar gibi) içeren dizindir. /usr ile ilgili söylenebilecek bir başka nokta da "local" klasörüdür. Linux, sunucu olarak birçok istemciye hizmet verebilecek bir işletim sistemidir. Bir Linux sunucu (server) kurarsanız, ona bağlanan yüzlerce istemci (client) olabilir. Her istemci bilgisayara, /usr altındaki programların ayrı ayrı yüklenmesi gerekmez; bir başka konumdan bu komutları çalıştırabilirsiniz. Ancak /usr altında bulunan "local" klasörü sadece kullandığınız makineye özeldir. Örneğin /usr/local/bin klasörü içinde bulunan bütün komutlar, direkt olarak kullandığınız makineye yüklenmiştir. /usr/bin komutları ise geneldir ve bir ağ üstündeki bütün makinelerden erişilebilir. Yani neticede "local" ifadesini gördüğünüzde, bunun sadece sizin makinenize özel olduğunu bilin.

### /var

Log dosyaları, e-posta ve yazıcı kuyrukları gibi değişken sistem bilgilerini barındırır. Sisteminize dair tutulan log'ları buradan görebilir; güvenlik durumunu buradan kontrol edebilirsiniz.

### /tmp

Geçici dosyalar içindir. Birçok program, burayı geçici depolama alanı olarak kullanır. /tmp klasörünün içeriği genellikle KB'lar mertebesinde kalır ve genellikle işletim sistemi yeniden başlarken içindeki dosyalar silinir. Her ne kadar tmp klasörü geçici dosyalar için de olsa bu klasör altında bulunan dosyaları, ne yaptığınızdan emin değilseniz, kesinlikle silmemelisiniz! Aksi taktirde sisteminizde ya da bazı programlarda birçok sorunla karşılaşabilirsiniz. Sistemi reboot ettiğinizde içindekiler siliniyor. Hacking saldırılarında da aslında yetkisini yükseltmek istediğimiz bir soyayı bu dizine koymamız avantaj sağlıyor. Gerekli  exploitleri burda kullanabiliyoruz. Kısaca yetki yükseltmekten bahsedecek olursam ilerde göreceğiz kullanıcılar çeşitli yetkileri olacak read, write, execute şeklinde ben bu üç yetkiye de sahipsem tam erişim sağlayabiliyorum ve chmod dediğim komutla bunu değiştirebiliyorum dediğim gibi tmp dizininde olmam bana avantaj sağlamış oluyor. Çünkü siliniyor.
