using Microsoft.Web.WebView2.Core;
using System.Drawing.Drawing2D;
using System.Security.Policy;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Sinema_Film_Fragmanları
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        private void Film_Bilgi_Load(string FilmAdi, string FilmBilgileri, string FilmPosteri, string FilmYorumları)
        {
            label1.Visible = true;
            label2.Visible = true;
            label3.Visible = true;
            label4.Visible = true;

            label1.Text = FilmAdi;
            label2.Text = FilmBilgileri;
            label3.Text = FilmPosteri;
            label4.Text = FilmYorumları;

        }
        private string url1 = "";
        private string url2 = "";

        //iKİ WEB VİEW AKTİF ETME FONKSİYONU
        private async Task İki_Web_View_Aktif_Et(string url1Param, string url2Param) //Param == Parameter (Parametre)
        {
            if (webView21.CoreWebView2 == null)
                await webView21.EnsureCoreWebView2Async(null);
            if (webView21.CoreWebView2 != null)
                webView21.CoreWebView2.Navigate(url1Param);

            if (webView22.CoreWebView2 == null)
                await webView22.EnsureCoreWebView2Async(null);
            if (webView22.CoreWebView2 != null)
                webView22.CoreWebView2.Navigate(url2Param);
        }

        private void filmYorumlarıToolStripMenuItem_Click(object sender, EventArgs e)
        {

        }

        private void yüzüklerinEfendisiToolStripMenuItem_Click(object sender, EventArgs e)
        {

        }

        private void webView21_Click(object sender, EventArgs e)
        {

        }

        private void uygulamaBilgiAlmaToolStripMenuItem_Click(object sender, EventArgs e)
        {
            MessageBox.Show("Uygulamamızda amacımız kullanıcıların kendi kategorilerinde popüler olan filmlerin fragmanlarını, posterlerini görebilmesi ve film ile ilgili bazı bilgilere erişmesini sağlamaktır.", "Bilgi Kutusu", MessageBoxButtons.OK, MessageBoxIcon.Information);
        }

        private void hakkımızdaToolStripMenuItem_Click(object sender, EventArgs e)
        {
            MessageBox.Show("Bu Uygulama Kaan Ata İnanç Tarfından Geliştirildi.", "Hakkımızda", MessageBoxButtons.OK, MessageBoxIcon.Information);
        }

        private void griToolStripMenuItem_Click(object sender, EventArgs e)
        {
            this.BackColor = Color.Gray;
            richTextBox1.BackColor = Color.Gray;
            webView21.DefaultBackgroundColor = Color.Gray;
            webView22.DefaultBackgroundColor = Color.Gray;
            label1.BackColor = Color.Gray;
            label2.BackColor = Color.Gray;
            label3.BackColor = Color.Gray;
            label4.BackColor = Color.Gray;

        }

        private void beyazToolStripMenuItem_Click(object sender, EventArgs e)
        {
            this.BackColor = Color.White;
            richTextBox1.BackColor = Color.White;
        }

        private void sarıToolStripMenuItem_Click(object sender, EventArgs e)
        {
            this.BackColor = Color.Orange;
            richTextBox1.BackColor = Color.Orange;
        }

        private void maviEskiHaliToolStripMenuItem_Click(object sender, EventArgs e)
        {
            this.BackColor = Color.SkyBlue;
            richTextBox1.BackColor = Color.SkyBlue;
        }

        private void çıkışToolStripMenuItem_Click(object sender, EventArgs e)
        {
            if (MessageBox.Show("Çıkmak İstediğinize Emin Misiniz?", "Çıkış Onayı", MessageBoxButtons.YesNo, MessageBoxIcon.Question) == DialogResult.Yes)
            {
                Application.Exit();
            }
        }

        //AKSİYON FİLMLERİ BAŞLANGICI
        private async void başlangıçToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=E-wMep9G32A&t=1s",
                "https://www.beyazperde.com/filmler/film-143692/kullanici-elestirileri/"
                );
            richTextBox1.Text = "Yönetmen: Christopher Nolan \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 16 Temmuz 2010 \n";
            richTextBox1.Text += "Süre: 2 Saat 28 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 8.8/10 \n";
            richTextBox1.Text += "Tür: Bilim Kurgu, Aksiyon \n";
            richTextBox1.Text += "Aldığı Ödüller : 4 Oscar, 3 BAFTA, 1 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Inception\", Cobb adlı bir hırsızın, bir kişinin bilinçaltına fikir yerleştirme görevi için bir araya getirdiği ekibin hikayesini anlatır. Ekip, çok katmanlı rüyalar aracılığıyla hedeflerine ulaşmaya çalışır ve Cobb, geçmişiyle yüzleşmek zorunda kalır. Filmin sonunda Cobb, çocuklarına kavuşsa da, gerçeklik ile rüya arasındaki çizginin belirsizliği devam eder.";
            pictureBox1.ImageLocation = "https://m.media-amazon.com/images/M/MV5BMjAxMzY3NjcxNF5BMl5BanBnXkFtZTcwNTI5OTM0Mw@@._V1_SX300.jpg";

            Film_Bilgi_Load("Başlangıç", "Film Bilgileri", "Film Posteri", "Film Yorumları");
            richTextBox1.Enabled = false;
        }

        private async void avatarToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=CM79GTEm2ps",
                "https://www.beyazperde.com/filmler/film-61282/kullanici-elestirileri/en-yeniler/"
                );
            //webView21.CoreWebView2.Navigate("");
            richTextBox1.Text = "Yönetmen: James Cameron \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 18 Aralık 2009 \n";
            richTextBox1.Text += "Süre: 2 Saat 42 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 7.9/10\n";
            richTextBox1.Text += "Tür: Bilim Kurgu, Macera \n";
            richTextBox1.Text += "Aldığı Ödüller : 3 Oscar, 2 BAFTA, 1 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Avatar\", 22. yüzyılda, insanların Pandora adlı bir ayda değerli bir mineral olan unobtaniumu çıkarmak için yerli Na'vi halkıyla çatışmasını konu alır. Jake Sully adlı bir eski deniz piyadesi, Na'vi bedenine bağlanarak onların dünyasına girer ve zamanla onların kültürünü benimser. Film, çevre koruma, sömürgecilik ve kimlik temalarını işler.";
            pictureBox1.ImageLocation = "https://cdn.img.anlatilaninotesi.com.tr/img/101440/54/1014405478_401:0:2001:1600_1920x0_80_0_0_6a581dbf63ff5ffc82f519201bee7f55.jpg";

            Film_Bilgi_Load("Film Adı: Avatar", "Film Bilgileri", "Film Posteri", "Film Yorumları");

        }

        private async void yüzüklerinEfendisiKralınDönüşüToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                  "https://www.youtube.com/watch?v=mO1yXwRfxGk\r\n",
                  "https://www.beyazperde.com/filmler/film-39187/kullanici-elestirileri/\r\n"
                  );
            //webView21.CoreWebView2.Navigate("https://www.youtube.com/watch?v=mO1yXwRfxGk");
            richTextBox1.Text = "Yönetmen: Peter Jackson \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 17 Aralık 2003 \n";
            richTextBox1.Text += "Süre: 3 Saat 21 Dakika \n";
            richTextBox1.Text += " IMDB Puanı: 9.0/10 \n";
            richTextBox1.Text += "Tür: Fantastik, Macera \n";
            richTextBox1.Text += "Aldığı Ödüller : 11 Oscar, 4 BAFTA, 4 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Yüzüklerin Efendisi: Kralın Dönüşü\", Frodo ve Sam'in Mordor'a doğru tehlikeli yolculuğunu ve Aragorn'un Gondor'un kralı olarak yükselişini konu alır. Film, Orta Dünya'nın kaderini belirleyecek büyük savaşları ve karakterlerin kişisel mücadelelerini işler. Sonunda, Yüzük yok edilir ve barış sağlanır.";
            pictureBox1.ImageLocation = "https://i.pinimg.com/474x/26/7c/45/267c45267d04aaaa72adc24150b168a6.jpg";

            Film_Bilgi_Load("Film Adı: Yüzüklerin Efendisi: Kralın Dönüşü", "Film Bilgileri", "Film Posteri", "Film Yorumları");

        }

        private async void karayipKorsanlarıDünyanınSonuToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                  "https://www.youtube.com/watch?v=HKSZtp_OGHY\r\n",
                  "https://www.beyazperde.com/filmler/film-57139/kullanici-elestirileri/en-yeniler/\r\n\r\n"
                  );
            //webView21.CoreWebView2.Navigate("https://www.youtube.com/watch?v=HKSZtp_OGHY");
            richTextBox1.Text = "Yönetmen: Gore Verbinski \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 25 Mayıs 2007 \n";
            richTextBox1.Text += "Süre: 2 Saat 49 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 7.1/10 \n";
            richTextBox1.Text += "Tür: Macera, Fantastik \n";
            richTextBox1.Text += "Aldığı Ödüller : 1 Oscar, 2 BAFTA, 0 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Karayip Korsanları: Dünyanın Sonu\", Jack Sparrow, Will Turner ve Elizabeth Swann'ın, Davy Jones'un kalbi ve denizlerin kontrolü için verdikleri mücadeleyi konu alır. Film, ihanetler, savaşlar ve beklenmedik ittifaklarla doludur. Sonunda, karakterler kendi kaderleriyle yüzleşir ve denizlerin geleceği belirlenir.";
            pictureBox1.ImageLocation = "https://img01.imgsinemalar.com/images/afis_buyuk/k/karayip-korsanlari-dunyanin-sonu-1660915289.jpg";

            Film_Bilgi_Load("Film Adı: Karayip Korsanları: Dünyanın Sonu", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }

        private async void hızlıVeÖfkeli10ToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                 "https://www.youtube.com/watch?v=1fvzVMmARqY\r\n",
                 "https://www.beyazperde.com/filmler/film-242871/kullanici-elestirileri/en-yeniler/\r\n"
                 );
            //webView21.CoreWebView2.Navigate("https://www.youtube.com/watch?v=1fvzVMmARqY");
            richTextBox1.Text = "Yönetmen: Justin Lin \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 19 Mayıs 2023 \n";
            richTextBox1.Text += "Süre: 2 Saat 10 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 6.6/10 \n";
            richTextBox1.Text += "Tür: Aksiyon, Suç \n";
            richTextBox1.Text += "Aldığı Ödüller : 0 Oscar, 0 BAFTA, 0 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Hızlı ve Öfkeli 10\", Dom Toretto ve ekibinin, uluslararası suç lordu Dante ile yüzleşmesini konu alır. Film, yüksek hızlı araba kovalamacaları, aksiyon dolu sahneler ve aile bağlarını vurgular. Sonunda, Dom ve ekibi, Dante'yi alt eder ve barışı sağlar.";
            pictureBox1.ImageLocation = "https://tr.web.img3.acsta.net/c_310_420/pictures/23/04/20/08/50/2513648.jpg";

            Film_Bilgi_Load("Film Adı: Fast and Furious 10", "Film Bilgileri", "Film Posteri", "Film Yorumları");

        }

        private async void hızlıVeÖfkeliHobbsVeShawToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=Ktf-rvnVX0g",
                "https://www.imdb.com/title/tt6806448/"
                );

            richTextBox1.Text = "Yönetmen: David Leitch \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 2 Ağustos 2019 \n";
            richTextBox1.Text += "Süre: 2 Saat 17 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 6.6/10 \n";
            richTextBox1.Text += "Tür: Aksiyon, Macera \n";
            richTextBox1.Text += "Aldığı Ödüller : 0 Oscar, 0 BAFTA, 0 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Hızlı ve Öfkeli: Hobbs ve Shaw\", Luke Hobbs ve Deckard Shaw'un, genetik olarak geliştirilmiş bir terörist olan Brixton ile mücadele etmek için zorunlu bir ortaklık kurmasını konu alır. Film, aksiyon dolu sahneler, yüksek tempolu kovalamacalar ve karakterlerin kişisel çatışmalarını içerir. Sonunda, Hobbs ve Shaw, Brixton'u alt eder ve dünyayı kurtarır.";

            Film_Bilgi_Load("Film Adı: Hızlı ve Öfkeli: Hobbs ve Shaw", "Film Bilgileri", "Film Posteri", "Film Yorumları");


            pictureBox1.ImageLocation = "https://tr.web.img2.acsta.net/r_1280_720/pictures/19/02/02/12/24/3087679.jpg";

        }

        private async void matrixToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=vKQi3bBA1y8\r\n",
                "https://www.beyazperde.com/filmler/film-19776/kullanici-elestirileri/\r\n"
                );
            richTextBox1.Text = "Yönetmen: The Wachowskis \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 31 Mart 1999 \n";
            richTextBox1.Text += "Süre: 2 Saat 16 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 8.7/10 \n";
            richTextBox1.Text += "Tür: Bilim Kurgu, Aksiyon \n";
            richTextBox1.Text += "Aldığı Ödüller : 4 Oscar, 2 BAFTA, 1 Altın Küre \n";
            richTextBox1.Text += "Konusu: \" Matrix, insanoğlunun ürettiği makinelerin(yapay zekanın), gelişmesi sonrasında, makineler tarafından meydana getirilen simülasyondur. İnsanlar bu simülasyonda tutsak olduklarını bilmeksizin yaşamlarını sürdürmektedir. Film, distopik bir geleceği tasvir eder.";

            pictureBox1.ImageLocation = "https://m.media-amazon.com/images/I/51vpnbwFHrL._AC_.jpg";
            Film_Bilgi_Load("Film Adı: Matrix", "Film Bilgileri", "Film Posteri", "Film Yorumları");


        }

        private async void cesurYürekToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=wj0I8xVTV18",
                "https://www.beyazperde.com/filmler/film-10080/kullanici-elestirileri/en-yeniler/"
                );
            richTextBox1.Text = "Yönetmen: Mel Gibson \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 24 Mayıs 1995 \n";
            richTextBox1.Text += "Süre: 2 Saat 57 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 8.3/10 \n";
            richTextBox1.Text += "Tür: Tarihi, Dram \n";
            richTextBox1.Text += "Aldığı Ödüller : 5 Oscar, 3 BAFTA, 2 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Cesur Yürek\", İskoç kahraman William Wallace'ın İngilizlere karşı verdiği özgürlük mücadelesini konu alır. Film, Wallace'ın kişisel trajedisi ve ulusal direnişi arasındaki dengeyi işler. Sonunda, Wallace ihanete uğrar ve idam edilir, ancak ölümü İskoçya'nın özgürlüğü için ilham kaynağı olur.";

            pictureBox1.ImageLocation = "https://m.media-amazon.com/images/I/51A7l8n2HkL._AC_.jpg";
            Film_Bilgi_Load("Film Adı: Cesur Yürek", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }

        private async void xMenBirinciSınıfToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=UrbHykKUfTM",
                "https://www.beyazperde.com/filmler/film-140894/kullanici-elestirileri/"
                );
            richTextBox1.Text = "Yönetmen: Matthew Vaughn \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 3 Haziran 2011 \n";
            richTextBox1.Text += "Süre: 2 Saat 12 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 7.7/10 \n";
            richTextBox1.Text += "Tür: Bilim Kurgu, Aksiyon \n";
            richTextBox1.Text += "Aldığı Ödüller : 0 Oscar, 1 BAFTA, 0 Altın Küre \n";
            richTextBox1.Text += "\"Konusu: \\XMen Birinci Sınıf\\\",Sebastian bir grup mutant ile Rusya ve Amerika arasında savaş çıkartmaya çalışmaktadır. Amacı Nükleer bomba sonrasında mutantların çoğaldığı gerekçesi ile mutant ırkını artırmak için iki süper gücü nükleer savaşa sürüklemektir. Bu arada bir Amerikan ajanı gizli bir soruşturma yürütürken mutantları keşfeder.";

            pictureBox1.ImageLocation = "https://m.media-amazon.com/images/I/51v5ZpFyaFL._AC_.jpg";
            Film_Bilgi_Load("Film Adı: XMen Birinci Sınıf", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }
        //AKSİYON FİLMLERİ KISMI BİTİŞİ

        //ROMANTİK FİLMLER KISMI BAŞLANGICI
        private async void titanikToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=LuPB43YSgCs",
                "https://www.beyazperde.com/filmler/film-5818/kullanici-elestirileri/en-yeniler/"
                );
            richTextBox1.Text = "Yönetmen: James Cameron \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: 19 Aralık 1997 \n";
            richTextBox1.Text += "Süre: 3 Saat 14 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 7.8/10 \n";
            richTextBox1.Text += "Tür: Romantik, Dram \n";
            richTextBox1.Text += "Aldığı Ödüller : 11 Oscar, 4 BAFTA, 4 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Titanic\", 1912'de batan RMS Titanic gemisinde geçen bir aşk hikayesini anlatır. Jack ve Rose, farklı sosyal sınıflardan gelmelerine rağmen birbirlerine aşık olurlar. Ancak gemi buzdağına çarpar ve trajik bir şekilde batar. Film, aşkın gücünü ve insan ruhunun direncini vurgular.";

            pictureBox1.ImageLocation = "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRlBHlxwXNcawxgnTD0cp84xpyOYCY8cuGaNQ&s";
            Film_Bilgi_Load("Film Adı: Titanic", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }
        private async void forrestGumpToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=bLvqoHBptjg",
                "https://www.beyazperde.com/filmler/film-10568/kullanici-elestirileri/en-yeniler/"
                );
            richTextBox1.Text = "Yönetmen: Robert Zemeckis \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi: \n 6 Temmuz 1994 \n";
            richTextBox1.Text += "Süre: 2 Saat 22 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 8.8/10 \n";
            richTextBox1.Text += "Tür: Romantik, Dram \n";
            richTextBox1.Text += "Aldığı Ödüller : 6 Oscar, 3 BAFTA, 2 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Forrest Gump\", düşük IQ'lu ama iyi kalpli Forrest Gump'ın hayatını anlatır. Forrest, tesadüfen Amerikan tarihinin önemli olaylarına tanıklık eder ve birçok başarıya imza atar. Film, sevgi, dostluk ve kader temalarını işler. Sonunda, Forrest, sevdiği kadın Jenny ile birlikte olur ve oğlunu büyütür.";

            pictureBox1.ImageLocation = "https://i.pinimg.com/170x/c9/bf/45/c9bf45942fc7899fd6c08cfbf70c3f76.jpg";
            Film_Bilgi_Load("Film Adı: Forrest Gump", "Film Bilgileri", "Film Posteri", "Film Yorumları");

        }

        private async void akılOyunlarıToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=Z07UN08TboY",
                " https://www.beyazperde.com/filmler/film-28384/kullanici-elestirileri/en-yeniler/\r\n"
                );
            richTextBox1.Text = "Yönetmen: Ron Howard \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi:\n 11 Aralık 2001 \n";
            richTextBox1.Text += "Süre: 2 Saat 15 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 8.2/10 \n";
            richTextBox1.Text += "Tür: Romantik, Dram \n";
            richTextBox1.Text += "Aldığı Ödüller : 4 Oscar, 2 BAFTA, 1 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Akıl Oyunları\", gerçek bir hikayeye dayanır ve matematik dehası John Nash'in hayatını anlatır. Nash, paranoid şizofreni ile mücadele ederken, hem akademik kariyerinde hem de kişisel hayatında zorluklarla karşılaşır. Film, aşkın ve azmin gücünü vurgular. Sonunda, Nash, hastalığını kontrol altına alır ve Nobel Ödülü kazanır.";

            pictureBox1.ImageLocation = "https://www.mudiposter.com/upload/66d4eaf9d5839aiapn56jjTvxJGMt0Y3ST18XCSi-1.jpg";
            Film_Bilgi_Load("Film Adı: Akıl Oyunları", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }

        private async void ilkÖpücükToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=p7_y-ZQ0ddg",
                "https://www.beyazperde.com/filmler/film-258023/kullanici-elestirileri/"
                );
            richTextBox1.Text = "Yönetmen: Murat Onbul \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi:\n 20 Ekim 2017 \n";
            richTextBox1.Text += "Süre: 1 Saat 50 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: Puanlama Yok \n";
            richTextBox1.Text += "Tür: Romantik \n";
            richTextBox1.Text += "Aldığı Ödüller : Ödül Yok \n";
            richTextBox1.Text += "Konusu:Hakan, Bağlanma korkusu olan ve sadece turistlerle kısa süreli ilişkiler yaşayan bir çapkındır. Hayatı, bir yaz günü kasabalarına gelen Bahar ile tanıştığında tamamen değişir. Ona ilk görüşte aşık olur, ancak Bahar'ın inanılmaz bir sırrı olduğunu keşfeder: İki yıl önce geçirdiği bir kaza sonucu, anterograd amnezi olarak da bilinen nadir bir hafıza kaybı yaşamaktadır. Bahar'ın beyni, kaza gününden sonra yaşadığı hiçbir yeni anıyı kaydedememektedir. Bu nedenle her sabah uyandığında, hayatının kaza gününde olduğunu sanır ve bir önceki günü hatırlamaz.\r\n\r\nBahar'ın abisi ve babası, onu bu acı gerçekten korumak ve mutlu etmek için her günü, kazanın olduğu o günmüş gibi yaşatmakta, evi ve çevreyi sürekli aynı tutmak için büyük bir çaba göstermektedir. Hakan da bu sıra dışı durumu öğrendikten sonra onlara katılır.\r\n\r\nArtık üçü birlikte, her günü Bahar için mükemmel kılmaya çalışırlar. Hakan'ın en büyük mücadelesi ise, her sabah sıfırdan başlamak ve bir önceki gün kendisine aşık olan kadını, o gün yeniden etkilemek ve ona aşık etmek zorunda olmasıdır. Bu, onun için hem umut dolu hem de her defasında kalbini kırması muhtemel zorlu bir aşk mücadelesine dönüşür. ";
            richTextBox1.Text += "Uyarlandığı Film:\n 2004 ABD Yapımı Romantik Film Olan 50 First Dates";

            pictureBox1.ImageLocation = "https://tr.web.img2.acsta.net/c_310_420/pictures/17/09/14/12/38/0194343.jpg";
            Film_Bilgi_Load("Film Adı: İlk Öpücük", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }

        private async void notSeniSeviyorumToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=b3BubMQtgJU",
                "https://www.beyazperde.com/filmler/film-111748/kullanici-elestirileri/en-yeniler/"
                );
            richTextBox1.Text = "Yönetmen: Nick Cassavetes \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi:\n 17 Şubat 2005 \n";
            richTextBox1.Text += "Süre: 2 Saat 3 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 7.8/10 \n";
            richTextBox1.Text += "Tür: Romantik, Dram \n";
            richTextBox1.Text += "Aldığı Ödüller : 0 Oscar, 0 BAFTA, 0 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Not: Seni Seviyorum\", genç bir kadın olan Holly ve onun kocası Gerry'nin hikayesini anlatır. Gerry, kanserden ölmeden önce Holly için bir dizi mektup yazar, her mektup onun hayatının belirli bir döneminde açılması için tasarlanmıştır. Holly, Gerry'nin ölümünden sonra bu mektupları alır ve her biri ona sevgi, cesaret ve yeni başlangıçlar için ilham verir. Film, aşkın ve kaybın gücünü vurgular.\n";
            richTextBox1.Text += "Uyarlandığı Kitap:\n 2004 Yapımı Romantik Dram Türündeki Nicholas Sparks'ın Aynı İsimli Romanı";

            pictureBox1.ImageLocation = "https://jetfilmizle.ltd/wp-content/posterler/2022/09/sevgili-john-izle.jpg";
            Film_Bilgi_Load("Film Adı: Not: Seni Seviyorum", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }

        private async void aşkTesadüfleriSeverToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=1qjMQ1xBldI",
                "https://www.beyazperde.com/filmler/film-189154/kullanici-elestirileri/"
                );
            richTextBox1.Text = "Yönetmen: Ömer Faruk Sorak \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi:\n 14 Şubat 2011 \n";
            richTextBox1.Text += "Süre: 1 Saat 58 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 6.0/10 \n";
            richTextBox1.Text += "Tür: Romantik, Dram \n";
            richTextBox1.Text += "Aldığı Ödüller : 0 Oscar, 0 BAFTA, 0 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Aşk Tesadüfleri Sever\", Zeynep ve Deniz'in hayatlarının çeşitli dönemlerinde tesadüfen karşılaşmalarını konu alır. İkisi de farklı şehirlerde büyümüş ve hayatlarının farklı yollarında ilerlemiş olsalar da, kader onları sürekli bir araya getirir. Film, aşkın ve kaderin gücünü vurgular. Sonunda, Zeynep ve Deniz, birbirlerini bulur ve birlikte olurlar.";

            pictureBox1.ImageLocation = "https://static.boxofficeturkiye.com/movie/poster/210x300/46/2010746-43571028.jpg";

            Film_Bilgi_Load("Film Adı: Aşk Tesadüfleri Sever", "Film Bilgileri", "Film Posteri", "Film Yorumları");

        }

        private async void cesaretinVToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=jNtBlVXo2Go",
                "https://www.beyazperde.com/filmler/film-46551/kullanici-elestirileri/en-yeniler/"
                );
            richTextBox1.Text = "Yönetmen: Yann Samuell \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi:\n 7 Eylül 2003 \n";
            richTextBox1.Text += "Süre 1 saat 33 dakika \n";
            richTextBox1.Text += "IMDB Puanı: 7.5/10 \n";
            richTextBox1.Text += "Tür: Romantik,Dram \n";
            richTextBox1.Text += "Aldığı Ödüller: \n Filmin Oscar, Bafta, Altın Küre Ödülü Bulunmamaktadır \n SXSW Film Festivali (2016), Mill Valley Film Festivali (2016) gibi alanlardan ödülleri vardır \n";
            richTextBox1.Text += "Konusu: Hikayenin kahramanları, Julien ve Sophie birbirleri için yaratılmış iki küçük çocuk. Julien’in annesi kanser, ölmek üzere. Sophie ise göçmenliğin zorluğu ile başa çıkmaya çalışıyor. Sophie ve Julien cesaret üzerine kurulu bir oyunla arkadaş olmak üzereler. Oyunun kuralı çok basit; sırasıyla her biri, ötekine cesaret gerektiren zorlu görevler veriyor. Bu görevler arasında sınava sütyenle gitmek de var, okulun en sert çocuğunu tokatlamak da. Julien ve Sophie bu kışkırtıcı oyunu zamanla hayatın ta kendisi haline getiriyorlar. Aradan geçen zaman, ikilinin arasına giren insanlar, kızgınlıklar ve hayal kırıklıkları hepsi oyunun aşılması gereken engellerine dönüşüyor. Julien ve Sophie’nin aralarında hayal gücünün sınırlarını zorlayan bir aşk yaratan bu oyun, maalesef aynı zamanda ikilinin birbirlerine kavuşmalarını da engelliyor. Şimdi bu iki genç aşığın önündeki son ve en zorlu görev, aşklarını yaratan bu yıkıcı oyunla başa çıkarak bir arada olmayı öğrenmek.";

            pictureBox1.ImageLocation = ("https://static.boxofficeturkiye.com/movie/poster/235x336/50/2004050-80856177@2x.jpg");
            Film_Bilgi_Load("Film Adı: Cesaretin Varmı Aşka", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }

        private async void kasımdaAşkBaşkadırToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=GaQaUud1k24",
                "https://www.beyazperde.com/filmler/film-29065/kullanici-elestirileri/"
                );
            richTextBox1.Text = "Yönetmen: Pat O'Connor \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi:\n 11 Mayıs 2001(Türkiye) \n";
            richTextBox1.Text += "Süre: 1 Saat 59 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 6.7/10 \n";
            richTextBox1.Text += "Tür: Romantik, Dram \n";
            richTextBox1.Text += "Aldığı Ödüller : 0 Oscar, 0 BAFTA, 0 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Kasımda Aşk Başkadır\", İrlanda'nın küçük bir kasabasında yaşayan Sarah ve Michael'ın hikayesini anlatır. Sarah, kocasını kaybettikten sonra hayatına devam etmeye çalışırken, Michael ise geçmişiyle yüzleşmeye çalışan bir adamdır. İkisi de Kasım ayında, kasabanın geleneksel festivalinde tanışır ve aralarında beklenmedik bir bağ oluşur. Film, aşkın ve kaybın gücünü vurgular.";

            pictureBox1.ImageLocation = "";

        }

        private async void turistToolStripMenuItem_Click(object sender, EventArgs e)
        {
            await İki_Web_View_Aktif_Et(
                "https://www.youtube.com/watch?v=zgFxHBgWT4I",
                "https://www.beyazperde.com/filmler/film-138752/kullanici-elestirileri/"
                );
            richTextBox1.Text = "Yönetmen: Florian Henckel von Donnersmarck \n";
            richTextBox1.Text += "Gösterime Giriş Tarihi:\n 14 Ocak 2011 \n";
            richTextBox1.Text += "Süre: 1 Saat 40 Dakika \n";
            richTextBox1.Text += "IMDB Puanı: 6.0/10 \n";
            richTextBox1.Text += "Tür: Romantik, Dram \n";
            richTextBox1.Text += "Aldığı Ödüller : 0 Oscar, 0 BAFTA, 0 Altın Küre \n";
            richTextBox1.Text += "Konusu: \"Turist\", Elise ve Frank'in hikayesini anlatır. Elise, zengin ve gizemli bir kadındır, Frank ise Amerikalı bir turisttir. İkisi, Alp dağlarında kayak yaparken tanışır ve aralarında beklenmedik bir çekim oluşur. Ancak Elise'in geçmişi ve niyetleri gizemlidir ve Frank, kendini tehlikeli bir oyunun içinde bulur. Film, aşkın ve güvenin sınandığı bir hikaye sunar.";

            pictureBox1.ImageLocation = "";
            Film_Bilgi_Load("Film Adı: The Tourist", "Film Bilgileri", "Film Posteri", "Film Yorumları");
        }
    }
}
