using System;
using System.Collections.Generic;

namespace generic_list
{
    class Program
    {
        static void Main(string[] args)
        {
            //List<T> class
            //System.Collections.Generic
            // T object tipindedir

            List<int> sayiListesi = new List<int>();

            sayiListesi.Add(23);
            sayiListesi.Add(10);
            sayiListesi.Add(4);
            sayiListesi.Add(5);
            sayiListesi.Add(92);
            sayiListesi.Add(34);

            List<string> renkListesi = new List<string>();
            renkListesi.Add("Kırmızı");
            renkListesi.Add("Mavi");
            renkListesi.Add("Turuncu");
            renkListesi.Add("Sarı");
            renkListesi.Add("Yeşil");

            //Count
            Console.WriteLine(sayiListesi.Count);
            Console.WriteLine(renkListesi.Count);

            //Foreach ve List.Foreach ile elamanlara erişim
            foreach (var sayi in sayiListesi)
            {
                Console.WriteLine(sayi);

            }
            
            foreach (var renk in renkListesi)
            {
                Console.WriteLine(renk);

            }

            sayiListesi.ForEach(sayi=> Console.WriteLine(sayi));
            renkListesi.ForEach(renk => Console.WriteLine(renk));

            //Listeden eleman çıkarma

            sayiListesi.Remove(4);
            renkListesi.Remove("Yeşil");

            sayiListesi.RemoveAt(0);
            renkListesi.RemoveAt(1);

            sayiListesi.ForEach(sayi=> Console.WriteLine(sayi));
            renkListesi.ForEach(renk => Console.WriteLine(renk));

            //Liste içerisinde arama
            if(sayiListesi.Contains(10))
            {
                Console.WriteLine("10 Liste içerisinde bulundu!");
            }

            //Eleman ile index'e erişme
            Console.WriteLine(renkListesi.BinarySearch("Sarı"));

            //Diziyi List'e çevirme

            string [] hayvanlar = {"Kedi","Köpek","Kuş"};
            List<string> hayvanListesi = new List<string>(hayvanlar);

            //Listeyi nasıl temizleriz
            hayvanListesi.Clear();
            
            //List içerisinde nesne tutmak

            List<Kullanıcılar> kullaniciListesi = new List<Kullanıcılar>();

            Kullanıcılar kullanıcı1 = new Kullanıcılar();
            kullanıcı1.Isim = "Ayşe";
            kullanıcı1.Soyisim = "Yılmaz";
            kullanıcı1.Yas=26;

            Kullanıcılar kullanıcı2 = new Kullanıcılar();
            kullanıcı2.Isim = "cansel";
            kullanıcı2.Soyisim = "gürsoy";
            kullanıcı2.Yas=24;

            kullaniciListesi.Add(kullanıcı1);
            kullaniciListesi.Add(kullanıcı2);

            List<Kullanıcılar> yeniListe = new List<Kullanıcılar>();

            yeniListe.Add(new Kullanıcılar(){
                Isim = "cansu",
                Soyisim ="gürsoy",
                Yas=23
            });

            foreach (var kullanıcı in kullaniciListesi)
            {
                Console.WriteLine("Kullanıcı Adı:"+ kullanıcı.Isim);
                Console.WriteLine("KUllanıcı Soyadı:"+kullanıcı.Soyisim);
                Console.WriteLine("KUllancıı Yası:"+kullanıcı.Yas);
                
            }

            
            

        }
    }

    public class Kullanıcılar
    {
        string isim;
        string soyisim;
        int yas;

        public string  Isim { get => isim; set=>isim = value; }

        public string Soyisim{ get => soyisim; set => soyisim =value;}

        public int Yas{get =>yas; set=>yas = value;}


    }
}
