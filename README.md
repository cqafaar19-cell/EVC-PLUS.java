import java.util.Scanner;

// Class-ka barnaamijka - waa qalabka ku talagalan nidaamka EVC PLUS (simulation)
public class EVC_PLUS {
    public static void main(String[] args) {
        Scanner input=new Scanner(System.in);
        System.out.println("Abdiqafaar Aweis Ali\nC1240267\n    Gali EVC codeka (*770#)");
        final int pin=1234; // Pin-ka sirta ah ee loo isticmaalo xaqiijinta account-ka
        final int haraaga=200; // Haraaga (balance) bilowga ah ee EVC PLUS
        String entry=input.next(); // Isticmaalaha wuxuu galiyaa code-ka (*770#)
        if (entry.equals("*770#")){ // Hubinta in code-ka la geliyay uu sax yahay
            System.out.println("--EVC_PLUS--");
            String[] Evc=new String[8]; // Array-ga ay ku jiraan menu-yada guud ee EVC PLUS
            Evc[0]="1.itus haraagara";
            Evc[1]="2.kaarka hadalka";
            Evc[2]="3.bixi bill";
            Evc[3]="4.u wareeji";
            Evc[4]="5.warbixin kooban";
            Evc[5]="6.salaam bank";
            Evc[6]="7.maareynta";
            Evc[7]="8.bill payment";
            System.out.println("fadlan gali pinkaga(Enter pin):");
            int Epin=input.nextInt(); // Pin-ka uu geliyay isticmaalaha
            if (Epin==pin){ // Hubinta in pin-ku sax yahay ka hor inta aan menu-ga la muujin
                for (int i=0; i<Evc.length; i++) { // Loop-ka ku daabaca dhammaan menu-yada
                    System.out.println(Evc[i]);
                }
                System.out.println("dooro");
                int option=input.nextInt(); // Doorashada isticmaalaha
                // Ku xiritaanka doorashada menu-ga ee la geliyay, mid kastaa u wareejinaya method gaar ah
                if (option==1){
                    haraga(haraaga);
                }
                else if (option==2){
                    kaarka_hadalka();
                } else if (option==3) {
                    bill();

                }else if (option==4) {
                    uwareeji(haraaga);
                } else if (option==5) {
                    warbaxinKooban();
                } else if (option==6) {
                    bankSalaam();

                } else if (option==7) {
                    maareyn(pin);
                } else if (option==8) {
                    Bill();
                }
            }

            else {
                System.out.println("wrong pin"); // Pin-ka waa qalad
            }


        }
        else
            System.out.println("wrong code"); // Code-ka la geliyay waa qalad


    }

    // Method: tusinta haraaga hadda jira ee account-ka
    public static void haraga(int haraa){
        System.out.println("haragaaga waa: "+haraa);
    }


    // Method: qaybta "kaarka hadalka" - waxay maamushaa airtime, MIFI, internet iyo shub qof kale
    public static void kaarka_hadalka() {
        Scanner input = new Scanner(System.in);
        final int haraaga=200;
        final int my_number = 612131112;
        System.out.println("             --kaarka hadalka--");
        System.out.println("1.ku shubo airtime");
        System.out.println("2.ugu shub airtime");
        System.out.println("3.MIFI packages");
        System.out.println("4.ku shubo internet");
        System.out.println("5.ugu shub qof kale (MMT)");
        System.out.println("dooro");
        int option = input.nextInt();
        switch (option) { // Switch-ka doorashada guud ee kaarka hadalka
            case 1: // Isku shubidda lambarkaaga
                System.out.println("fadlan gali lacagta:");
                int money = input.nextInt();
                System.out.println("Ma hubta in  $" + money + " ugu shubtid undefined");
                System.out.println("1.haa");
                System.out.println("2.maya");
                int choose = input.nextInt();
                if (choose == 1 && money <= 200) // Hubinta xaddiga lacagta iyo ogolaanshaha
                    System.out.println("waxaad $" + money + " ugu shubtay " + my_number + "\n Mahadsanid");
                else
                    System.out.println("wa la joojiyay");
                break;
            case 2: // U shubidda qof kale (validation number)
                System.out.println("fadlan gali lambarka:");
                String num = input.next();
                // Hubinta qaabka lambarka - waa inuu ku bilaabmaa +252, 06, 00252 ama 6, dhererkuna sax yahay
                if (num.startsWith("+252") && String.valueOf(num).length() == 13
                        || num.startsWith("06") && String.valueOf(num).length() == 10
                        || num.startsWith("00252") && String.valueOf(num).length() == 14
                        || num.startsWith("6") && String.valueOf(num).length() == 9) {
                    System.out.println("gali lacagta:");
                    money = input.nextInt();
                    if (money <= 200) {
                        System.out.println("ma hubta inaad $" + money + " u wareejiso " + num);
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose = input.nextInt();
                        if (choose == 1)
                            System.out.println("waxaad $" + money + " ugu shubtay " + num + "\n Mahadsanid");
                        else
                            System.out.println("Mahadsanid wa la joojiye");
                    } else {
                        System.out.println("ivalid money");
                    }

                } else
                    System.out.println("number not exists.\n Mahadsanid");
                break;
            case 3: // Qaybta MIFI packages - xirmooyinka maalinle, isbuucle, iyo bille
                System.out.println("1.ku shubo data-da MIFI");
                choose = input.nextInt();
                if (choose == 1) {
                    System.out.println("1.maalinle");
                    System.out.println("2.isbuucle");
                    System.out.println("3.bille");
                    option = input.nextInt();

                    switch (option) { // Switch-ka nooca xirmada MIFI (maalinle/isbuucle/bille)
                        case 1: // Xirmooyinka maalinle
                            System.out.println("1.1$=3GB");
                            System.out.println("2.2$=5GB");
                            choose = input.nextInt();
                            if (choose == 1) {
                                System.out.println("Gali MIFI user");
                                String MIFI = input.next();
                                if (String.valueOf(MIFI).length() == 6) { // Hubinta dhererka MIFI user-ka
                                    System.out.println("ma hubta ina ku shubato 1$");
                                    System.out.println("1.haa");
                                    System.out.println("2.maya");
                                    option = input.nextInt();
                                    if (option == 1)
                                        System.out.println("waxaad heshay 3GB data oo ah MIFI \n mahadsaind");
                                    else
                                        System.out.println("mahadsanid");
                                } else
                                    System.out.println("lenghth of MIFI USER IS WRONG");


                            } else if (choose == 2) {
                                System.out.println("Gali MIFI user");
                                String MIFI = input.next();
                                if (String.valueOf(MIFI).length() == 6) {
                                    System.out.println("ma hubta ina ku shubato 3$");
                                    System.out.println("1.haa");
                                    System.out.println("2.maya");
                                    option = input.nextInt();
                                    if (option == 1)
                                        System.out.println("waxaad heshay 5GB data oo ah MIFI \n mahadsaind");
                                    else
                                        System.out.println("mahadsanid");
                                } else
                                    System.out.println("lenghth of MIFI USER IS WRONG");


                            }
                            break;
                        case 2: // Xirmooyinka isbuucle
                            System.out.println("1.5$=12GB");
                            System.out.println("2.10$=30GB");
                            choose = input.nextInt();
                            if (choose == 1) {
                                System.out.println("Gali MIFI user");
                                String MIFI = input.next();
                                if (String.valueOf(MIFI).length() == 6) {
                                    System.out.println("ma hubta ina ku shubato 5$");
                                    System.out.println("1.haa");
                                    System.out.println("2.maya");
                                    option = input.nextInt();
                                    if (option == 1)
                                        System.out.println("waxaad heshay 12GB data oo ah MIFI \n mahadsaind");
                                    else
                                        System.out.println("mahadsanid");
                                } else
                                    System.out.println("lenghth of MIFI USER IS WRONG");


                            } else if (choose == 2) {
                                System.out.println("Gali MIFI user");
                                String MIFI = input.next();
                                if (String.valueOf(MIFI).length() == 6) {
                                    System.out.println("ma hubta ina ku shubato 10$");
                                    System.out.println("1.haa");
                                    System.out.println("2.maya");
                                    option = input.nextInt();
                                    if (option == 1)
                                        System.out.println("waxaad heshay 30GB data oo ah MIFI \n mahadsaind");
                                    else
                                        System.out.println("mahadsanid");
                                } else
                                    System.out.println("lenghth of MIFI USER IS WRONG");


                            }
                            break;
                        case 3: // Xirmooyinka bille
                            System.out.println("1.20$=50GB");
                            System.out.println("2.30$=70GB");
                            choose = input.nextInt();
                            if (choose == 1) {
                                System.out.println("Gali MIFI user");
                                String MIFI = input.next();
                                if (String.valueOf(MIFI).length() == 6) {
                                    System.out.println("ma hubta ina ku shubato 20$");
                                    System.out.println("1.haa");
                                    System.out.println("2.maya");
                                    option = input.nextInt();
                                    if (option == 1)
                                        System.out.println("waxaad heshay 50GB data oo ah MIFI \n mahadsaind");
                                    else
                                        System.out.println("mahadsanid");
                                } else
                                    System.out.println("lenghth of MIFI USER IS WRONG");


                            } else if (choose == 2) {
                                System.out.println("Gali MIFI user");
                                String MIFI = input.next();
                                if (String.valueOf(MIFI).length() == 6) {
                                    System.out.println("ma hubta ina ku shubato 30$");
                                    System.out.println("1.haa");
                                    System.out.println("2.maya");
                                    option = input.nextInt();
                                    if (option == 1)
                                        System.out.println("waxaad heshay 70GB data oo ah MIFI \n mahadsaind");
                                    else
                                        System.out.println("mahadsanid");
                                } else
                                    System.out.println("lenghth of MIFI USER IS WRONG");


                            }
                    }

                }
                break;
            case 4: // Qaybta shubidda internet-ka - xirmo kala duwan
                System.out.println("Fadlan dooro xirmada ku shubeyso");
                System.out.println("1.isbuucle(weekly)");
                System.out.println("2.time based packages");
                System.out.println("3.DATA");
                System.out.println("4.maalinle(daily)");
                System.out.println("5.bille(MIFI)");
                System.out.println("dooro");
                option = input.nextInt();
                if (option == 1) { // Xirmo isbuucle
                    System.out.println("gali lacagta");
                    int lacagta = input.nextInt();
                    if (lacagta <= 200) {
                        System.out.println("ma hubta ina ku shubato " + lacagta);
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose = input.nextInt();
                        if (choose == 1)
                            System.out.println("waxaad ku shubatay " + lacagta + " isbuucle(weekly)\nMahadsanid");
                        else
                            System.out.println("Mahadsanid!");
                    }
                    else
                        System.out.println("Lacagta kuguma filna");
                }
                else if (option == 2) { // Time based packages
                    System.out.println("gali lacagta");
                    int lacagta1 = input.nextInt();
                    if (lacagta1 <= 200) {
                        System.out.println("ma hubta ina ku shubato " + lacagta1);
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose = input.nextInt();
                        if (choose == 1)
                            System.out.println("waxaad ku shubatay " + lacagta1 + " TIME BASED PACKAGE\nMahadsanid");
                        else
                            System.out.println("Mahadsanid!");
                    }
                    else
                        System.out.println("lacagta kuguma filna");

                } else if (option == 3) { // DATA
                    System.out.println("gali lacagta");
                    int lacagta2 = input.nextInt();
                    if (lacagta2 <= 200) {
                        System.out.println("ma hubta ina ku shubato " + lacagta2);
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose = input.nextInt();
                        if (choose == 1)
                            System.out.println("waxaad ku shubatay " + lacagta2 + " DATA\nMahadsanid");
                        else
                            System.out.println("Mahadsanid!");
                    }
                    else
                        System.out.println("lacagta kuguma filna");
                } else if (option == 4) { // Maalinle (daily)
                    System.out.println("gali lacagta");
                    int lacagta3 = input.nextInt();
                    if (lacagta3 <= 200) {
                        System.out.println("ma hubta ina ku shubato " + lacagta3);
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose = input.nextInt();
                        if (choose == 1)
                            System.out.println("waxaad ku shubatay " + lacagta3 + " Maalinle(daily)\nMahadsanid");
                        else
                            System.out.println("Mahadsanid!");
                    } else
                        System.out.println("lacagta kuguma filna");
                }else if (option == 5) { // Bille (MIFI)
                    System.out.println("gali lacagta");
                    int lacagta3 = input.nextInt();
                    if (lacagta3 <= 200) {
                        System.out.println("ma hubta ina ku shubato " + lacagta3);
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose = input.nextInt();
                        if (choose == 1)
                            System.out.println("waxaad ku shubatay " + lacagta3 + " bille(monthly)\nMahadsanid");
                        else
                            System.out.println("Mahadsanid!");
                    } else
                        System.out.println("lacagta kuguma filna");
                }
                break;
            case 5: // U shubidda qof kale (MMT)
                System.out.println("fadlan gali lambarka");
                num=input.next();
                if (num.startsWith("+252") && String.valueOf(num).length() == 13
                        || num.startsWith("06") && String.valueOf(num).length() == 10
                        || num.startsWith("00252") && String.valueOf(num).length() == 14
                        || num.startsWith("6") && String.valueOf(num).length() == 9){
                    System.out.println("gali lacgta");
                    money=input.nextInt();
                    if (money<200){
                        System.out.println("ma hubta ina "+money+" ugu shubto "+num);
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose=input.nextInt();
                        if (choose==1)
                            System.out.println("waxaad "+money+" ugu shubtay "+num+"\n Mahadsanid");
                        else
                            System.out.println("Thanks!!");

                    }else
                        System.out.println("invalid currency");
                }


        }


    }

    // Method: bixinta biilasha - waxay maamushaa post paid iyo ku iibsiga
    public static void bill(){
        Scanner input=new Scanner(System.in);
        final int haraaga=200;
        final int biil=400;
        int option=0;
        System.out.println("    bixi bill");
        System.out.println("1.post paid");
        System.out.println("2.ku iibso");
        int choose=input.nextInt();
        if (choose==1){ // Qaybta post paid
            System.out.println("    post paid");
            System.out.println("1.ogow biilka");
            System.out.println("2.bixi bill");
            System.out.println("3.ka bixi bill");
            System.out.println("dooro");
            option=input.nextInt();
            switch (option){ // Switch-ka doorashada post paid
                case 1: // Ogaanshaha lacagta biilka
                    System.out.println("Bill kaga waa "+biil);
                    break;
                case 2: // Bixinta biilka oo dhan
                    System.out.println("fadlan geli lacagta");
                    int money=input.nextInt();
                    if (money<=400){
                        System.out.println("ma hubta in bixiso "+money+" bill");
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose=input.nextInt();
                        if (choose==1)
                            System.out.println("waxaad bixisay "+money+"bill kaga wa"+(biil-money));

                    }else
                        System.out.println("invalid money");

                    break;
                case 3: // Bixinta biilka qof kale (lambarka kale)
                    System.out.println("Fadlan gali lambar");
                    int num=input.nextInt();
                    System.out.println("gali  lacagta");
                    money=input.nextInt();
                    if (money<biil){
                        System.out.println("ma hubta ina ka "+money+" ka bixiso tell no"+num);
                        System.out.println("1.haa");
                        System.out.println("2.maya");
                        choose=input.nextInt();
                        if (choose==1)
                            System.out.println("waxaad "+money+" bill ka bixise tell no:"+num+
                                    "haragaaga waa"+(biil-money)+"\nMahadsanid");

                    }else
                        System.out.println("invalid money");



            }


        }
        else if (choose==2){ // Qaybta ku iibsiga (xaqiijinta aqoonsi ganacsi)
            int aqoonsi=1240267;
            System.out.println("fadlan geli aqoonsigaga ganacsiga");
            int answer=input.nextInt();
            while(aqoonsi!=answer){ // Loop-ka sii celceliya ilaa aqoonsigu saxsanaado
                System.out.println("inavlid input \n Fadlan geli aqoosiga ganacsiga");
                answer=input.nextInt();

            }
            System.out.println("you got it");


        }else
            System.out.println("wrong choose");


    }

    // Method: u wareejinta lacagta lambar kale (transfer)
    public static void uwareeji(int lacag){
        Scanner input=new Scanner(System.in);
        final int haraaga=200;
        System.out.println("fadlan gali lambarka");
        String num=input.next();
        // Hubinta qaabka lambarka la geliyay
        if (num.startsWith("+252") && String.valueOf(num).length() == 13
                || num.startsWith("06") && String.valueOf(num).length() == 10
                || num.startsWith("00252") && String.valueOf(num).length() == 14
                || num.startsWith("6") && String.valueOf(num).length() == 9){
            System.out.println("gali lacagta");
            int money =input.nextInt();
            if (money<=haraaga){ // Hubinta in lacagtu ka yartahay ama la mid tahay haraaga
                System.out.println("Ma hubta ina u wareejiso $"+money+" lambarka "+num);
                System.out.println("1.maya");
                System.out.println("2.haa");
                int choose=input.nextInt();
                if (choose==2)
                    System.out.println("waxaad $"+money+" u wareejisay lambarka "+num+" haraagaga waa "+(haraaga-money));
                else if (choose==1) {
                    System.out.println("mahadsanid!!");
                }

            }else
                System.out.println("haragaga kuguma filna");


        }else
            System.out.println("number not exists");
    }


    // Method: warbixin kooban - taariikhda dhaqdhaqaaqyada u danbeeyay
    public static void warbaxinKooban(){
        Scanner input=new Scanner(System.in);
        final String last1="Waxaad $60 u wareejisay 617620115\nMahadsanid";
        final String last2="Waxaad $100 ka heshay 617620115\nMahadsanid";
        final String last3="Waxaad $60 u wareejisay 617819303\nMahadsanid";
        final String iibasasho="Waxaad 150 ku shubta bankName: Jamhuuriya university\nMahadsanid";
        int option=0;
        System.out.println("   warbixin koobana");
        System.out.println("1.last action");
        System.out.println("2.wareejinti u danbeyse");
        System.out.println("3.iisashadii u danbeyse");
        System.out.println("4.last 3 action");
        System.out.println("dooro");
        int choose=input.nextInt();
        if (choose==1){ // Dhaqdhaqaaqii ugu danbeeyay
            System.out.println(last1);
        } else if (choose==2) { // Wareejintii u danbeysay - loo baahan yahay hubin lambarka
            System.out.println("1.u wareejisay");
            System.out.println("2.ka heshay");
            option=input.nextInt();
            if (option==1){
                System.out.println("Gali lambarka");
                int num=input.nextInt();
                if (num==617620115)
                    System.out.println(last1);
                else if (num==617819303)
                    System.out.println(last3);
                else
                    System.out.println("no transaction");

            } else if (option==2) {
                System.out.println("Gali lambarka");
                int num=input.nextInt();
                if (num==617620115)
                    System.out.println(last2);
                else
                    System.out.println("no transaction");
            }else
                System.out.println("invalid option");

        } else if (choose==3) { // Iibsashadii ugu danbeysay - hubin bank name
            System.out.println("gali bankName ee aad ka iibsate");
            String optn=input.next();
            if (optn.equals("Jamhuriya University"))
                System.out.println(iibasasho);
            else
                System.out.println("no transaction happen");

        } else if (choose==4) { // Muujinta saddexdii dhaqdhaqaaq ee ugu danbeeyay
            System.out.println(last1);
            System.out.println(last2);
            System.out.println(last3);

        }


    }

    // Method: Salaam Bank - xiriirinta account-ka bank-ka iyo EVC PLUS
    public static void bankSalaam(){
        Scanner input=new Scanner(System.in);
        final int bill=400;
        final int haraa=200;
        final String account="Abdiqafaar267"; // Account-ka la rabo in la hubiyo
        System.out.println("   Salaam Bank");
        System.out.println("1.Itus haraaga ");
        System.out.println("2.lacag dhigasho");
        System.out.println("3.lacag qaadasho");
        System.out.println("4.Ka wareeji EVC_PLUS");
        int choose=input.nextInt();
        switch (choose){ // Switch-ka doorashada Salaam Bank
            case 1: // Ogaanshaha haraaga bank-ka
                System.out.println("Gali Account kaga");
                String bank=input.next();
                if (bank.equals(account))
                    System.out.println("Haraagaga wa $"+bill);
                else
                    System.out.println("wrong account");
                break;

            case 2: // Lacag dhigasho (deposit)
                System.out.println("Gali account kaga");
                bank=input.next();
                if (bank.equals(account)){
                    System.out.println("Gali lacagta");
                    int money=input.nextInt();
                    System.out.println("waxaad lacag dhigatay bank account kaga\nHaragaaga wa $"+(bill+money));

                }else
                    System.out.println("wrong account");
                break;

            case 3: // Lacag qaadasho (ka wareejin bank -> EVC PLUS)
                System.out.println("gali Account kaga");
                bank=input.next();
                if (bank.equals(account)) {
                    System.out.println("gali lacagta");
                    int money=input.nextInt();
                    if (money<400){
                        System.out.println("haraagaga EVC_PLUS waxaa lagu kordhiye $"+money+
                                "\nHaragaaga waa"+(money+haraa));


                    }else
                        System.out.println("haraagaga kuguma filna");
                }
                else
                    System.out.println("Wrong account");
                break;
            case 4: // Ka wareejinta EVC PLUS xagga bank-ka
                System.out.println("gali account kaga");
                bank=input.next();
                if (bank.equals(account)){
                    System.out.println("gali lacagta");
                    int money=input.nextInt();
                    if (money<=haraa){
                        System.out.println("Haragaaga bank account waxaa lagu kordhiyaya $"+money+
                                "\nHaraagaga waa $"+(money+bill));
                    }else
                        System.out.println("haraagaga kuguma filna");

                }else
                    System.out.println("wrong account");


        }
    }

    // Method: maareynta account-ka - bedelka pin, luqadda, lacag xirasho, iyo u celinta lacagta
    public static void maareyn(int pin){
        Scanner input=new Scanner(System.in);
        final int haraa=200;
        int num=617620115;
        int money=10;
        String wrong="waxaad "+money+" U wareejisay "+num+" haraagaga wa "+(haraa-money);
        System.out.println("   maareynta");
        System.out.println("1.Bedel lambarka sirta ");
        System.out.println("2.Bedel luqadda");
        System.out.println("3.lacag xirasho");
        System.out.println("4.u celi lacag");
        System.out.println("dooro");
        int option=input.nextInt();
        if (option==1){ // Bedelka pin-ka - hubi pin-ka hore, geli mid cusub, xaqiiji
            System.out.println("gali pinKaga hore");
            int pin1=input.nextInt();
            if (pin1==pin && String.valueOf(pin1).length()==4){
                System.out.println("Gali pinkaga cusub");
                int Npin=input.nextInt();
                if (String.valueOf(Npin).length()==4){
                    System.out.println("hubi pin kaga Cusub");
                    int ChNPin=input.nextInt();
                    if (ChNPin==Npin)
                        System.out.println("Waad ku guuleysatay badalida pin kaga\nMahadsanid");
                    else
                        System.out.println("pin not matching");

                }else
                    System.out.println("Waa ino ka koobnaada 4 digit\nMahadsanid");


            }else
                System.out.println("Invalid pin");


        } else if (option==2) { // Bedelka luqadda
            System.out.println("    Dooro Luqada aa rabto");
            System.out.println("1.English");
            System.out.println("2.Somali");
            int choose=input.nextInt();
            if (choose==1)
                System.out.println("You can successful to Change your language\nThanks");
            else
                System.out.println("Waad ku guuleysatay bedelida binkaga");


        } else if (option==3) { // Lacag xirasho - u dirid qof aan si qalad u qorin
            System.out.println("Fadlan gali lambarka ku qalade");
            int qaladay=input.nextInt();
            System.out.println("Gali lambarka u wade");
            int Chqaladay=input.nextInt();
            if (qaladay==num){
                System.out.println("gali lacagta ");
                int money1=input.nextInt();
                if (money1==money)
                    System.out.println("Wa laguu xayire");
                else
                    System.out.println("Lacag aad galisay wa qalad!!!");


            }else{
                System.out.println("Gali lacagta ");
                money=input.nextInt();

                System.out.println("Sorry wax wax transaction kuuma yaalo\nMahadasanid");
            }



        } else if (option==4) { // U celinta lacagta dhaqdhaqaaqii qaladka ahaa
            System.out.println("Fadlan gali lambarka");
            int qalday=input.nextInt();
            System.out.println("Fadlan gali lacagta");
            int lacag=input.nextInt();
            if (qalday==num && lacag==money){
                System.out.println("koontadaada waxa laga jare $"+lacag+" haraagaga waa $"+(haraa-lacag));

            }else
                System.out.println("No Transaction happens");

        }

    }

    // Method: bixinta biilasha adigoo isticmaalaya reference number (itus, wada bixi, qeyb bixi)
    public static void Bill(){
        Scanner input=new Scanner(System.in);
        int haraa=200;
        final int bill_reference_number=240267; // Lambarka la aqoonsan karo biilka
        int payable=250; // Lacagta guud ee la bixinayo
        System.out.println("1.itus haraaga bill ka:");
        System.out.println("2.wado bixi bill ka:");
        System.out.println("3.qeyb ka bixi bill ka:");
        int choose=input.nextInt();
        if (choose==1){ // Ogaanshaha lacagta la bixinayo
            System.out.println("gali refernce bill numberkaga");
            int enter=input.nextInt();
            if (enter==bill_reference_number)
                System.out.println("haraagaga bill payment wa $"+haraa);
            else
                System.out.println("wrong reference number ");
        } else if (choose==2) { // Wada bixinta biilka oo dhan
            System.out.println("gali refernce bill numberkaga");
            int enter=input.nextInt();
            if (enter==bill_reference_number){
                System.out.println("Total bill lagugu leyahay wa $"+payable+" :\nMahubta inaad bixi bill $"+payable+"\n1.haa\n2.maya");
                int choise=input.nextInt();
                if (choise==1){
                    if (haraa>payable) { // Hubinta in haraagu kufilan yahay bixinta
                        haraa=haraa-payable;
                        System.out.println("Waad wada bixisay bill ka haraagaga wa $"+haraa +"\nMahadsanid");

                    }else
                        System.out.println("Haraagaga kuguma filna");


                }else
                    System.out.println("mahadsanid");

            }else
                System.out.println("Wrong reference number");
        } else if (choose==3) { // Qeyb ka bixinta biilka (bixin dhinaceed)
            System.out.println("gali refernce bill numberkaga");
            int enter=input.nextInt();
            if (enter==bill_reference_number){
                System.out.println("Lacagta lagugu leyahy wa $"+payable);
                System.out.println("imisa ayaad bixineysaa");
                int paying=input.nextInt();
                if (paying<haraa){ // Hubinta in lacagta la bixinayo ka yartahay haraaga
                    System.out.println("ma habta in bill cadadisa tahay $"+payable+" aad ka bixiso $"+paying+" \n1.haa\n2.maya");
                    int choise=input.nextInt();
                    if (choise==1){
                        haraa=haraa-paying;
                        payable=payable-paying;
                        System.out.println("Waxad bixisay $"+paying+" haraagaga waa $"+haraa+"\nlacagta lagugu leyhy wa "+payable);
                    }else
                        System.out.println("Mahadsanid");
                }else
                    System.out.println("haragaga kuguma filna");
            }

        }


    }
}
