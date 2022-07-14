# Kullan-c-Giri-i-
Eğer şifre yanlış ise kullanıcıya şifresini sıfırlayıp sıfırlamayacağını sorun, eğer kullanıcı sıfırlamak isterse yeni girdiği şifrenin hatalı girdiği ve unuttuğu şifre ile aynı olmaması gerektiğini kontrol edip , şifreler aynı ise ekrana "Şifre oluşturulamadı, lütfen başka şifre giriniz." sorun yoksa "Şifre oluşturuldu" yazan programı yazınız.ve kullanıcı adı yanlışsa yeni kullanıcı adı oluşturunuz ama eski yazmış olduğumuz kullanıcı adı ile aynı olmayacak,sorun olmassa kullanıcı adıda oluştu programı yazınız

     import java.util.Scanner;

     public class Main {
  
    public static void main(String[] args) {
        String userName, passWord, newpassword, newUserName;
        int sifreYenileme, kullanıcıAdıYenileme;

        Scanner inp = new Scanner(System.in);

        System.out.print("Kullanıcı Adınız :");
        userName = inp.nextLine();

        System.out.print("Şifreniz :");
        passWord = inp.nextLine();

        if (userName.equals("patika") && passWord.equals("java123")) {
            System.out.println("Giriş Yaptınız ! ");

        } else if (userName != "patika" && passWord.equals("java123")) {
            System.out.print("Kullanıcı adı hatalı kullanıcı adınızı yenilemek istermisiniz evet için 1'i hayır için 2'yi basın :");
            kullanıcıAdıYenileme = inp.nextInt();


            if (kullanıcıAdıYenileme == 1) {
                System.out.print("Yeni Kullanıcı adı giriniz :");
                newUserName = inp.next();
                if (newUserName.equals("patika") || newUserName.equals(userName)) {
                    System.out.println("Yeni Kullanıcı Adı oluşmadı(Eski Kullanıcı Adıyla Aynı Olmamasına Özen Gösteriniz !");
                } else {
                    System.out.print("Yeni Kullanıcı Adı Oluştu !");
                }
            }
        } else if (userName.equals("patika") && passWord != "java123") {
            System.out.print("Şifreniz Hatalı Şifreyi  Sıfırlamak İstermiziniz ? evet için 1'i hayır için 2'yi tuşlayınız : ");
            sifreYenileme = inp.nextInt();

            switch (sifreYenileme) {
                case 1:
                    System.out.print("Yeni Şifreyi Giriniz :");
                    newpassword = inp.next();
                    if (newpassword.equals("java123") || newpassword.equals(passWord)) {
                        System.out.println("Yeni Şifre Oluşmadı(Eski Şifre ile Aynı Olmamasına Özen Gösteriniz !");
                    } else {
                        System.out.println("Şifre Oluşturuldu");
                    }
                    break;
            }
        } else {
            System.out.println("Kullanıcı Adınız Veya Şifre Hatalı");
        }

    }
}
