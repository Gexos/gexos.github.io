---
layout: post
title: # Ποια είναι η διαφορά μεταξύ του HTTP και του HTTPS;
tags: [http]
---

Πάντα ενθαρρύνω τους ανθρώπους να κάνουν τη μετάβαση στο HTTPS για διάφορους λόγους, όπως οφέλη απόδοσης, πρόσθετη ασφάλεια, ακόμη και πλεονεκτήματα SEO. Έτσι, σκέφτηκα να διερευνήσουμε σε βάθος τη διαφορά μεταξύ HTTP και HTTPS, τι σημαίνουν και γιατί ίσως ήρθε η ώρα να κάνετε τη μετάβαση στο HTTPS. 
<!--more-->
## Τι είναι το HTTP;

Το HTTP σημαίνει Hypertext Transfer Protocol (Πρωτόκολλο μεταφοράς υπερκειμένου). Όταν εισάγουμε http:// στη γραμμή διευθύνσεων λέμε στο πρόγραμμα περιήγησης να συνδεθεί μέσω HTTP. Το HTTP χρησιμοποιεί το [TCP](https://el.wikipedia.org/wiki/%CE%A0%CF%81%CF%89%CF%84%CF%8C%CE%BA%CE%BF%CE%BB%CE%BB%CE%BF_%CE%95%CE%BB%CE%AD%CE%B3%CF%87%CE%BF%CF%85_%CE%9C%CE%B5%CF%84%CE%AC%CE%B4%CE%BF%CF%83%CE%B7%CF%82/%CE%A0%CF%81%CF%89%CF%84%CF%8C%CE%BA%CE%BF%CE%BB%CE%BB%CE%BF_%CE%94%CE%B9%CE%B1%CE%B4%CE%B9%CE%BA%CF%84%CF%8D%CE%BF%CF%85) (Transmission Control Protocol) και τη θύρα 80, για την αποστολή και λήψη δεδομένων μέσω του web. Για να το πούμε απλά, είναι ένα πρωτόκολλο που χρησιμοποιείται από έναν πελάτη (client) και έναν διακομιστή (server) και μας επιτρέπει να επικοινωνούμε με άλλους ιστότοπους. Ο πελάτης στέλνει ένα μήνυμα αιτήματος σε έναν διακομιστή HTTP (μετά τη [χειραψία-handshake TCP](https://developer.mozilla.org/en-US/docs/Glossary/TCP_handshake) που φιλοξενεί έναν ιστότοπο, ο διακομιστής στη συνέχεια στέλνει μια απάντηση.

Το TCP είχε βελτιώσεις με την πάροδο των ετών, αλλά ως επί το πλείστον είναι το ίδιο με αυτό που ήταν όταν ορίστηκε για πρώτη φορά το 1974, [RFC675](https://tools.ietf.org/html/rfc675). Το HTTP χρησιμοποιεί επίσης το UDP (User Datagram Protocol). Είναι λιγότερο αξιόπιστο, αλλά χρησιμοποιείται ευρέως σε τηλεδιασκέψεις, βιντεοπαιχνίδια κλπ. Επιτρέπει την απόρριψη και λήψη μεμονωμένων πακέτων με διαφορετική σειρά για καλύτερη απόδοση.

Εάν υπάρχει κάποιο πρόβλημα με ένα αίτημα HTTP, υπάρχει μια λίστα με κωδικούς που ενημερώνουν το πρόγραμμα περιήγησής σας έτσι ώστε να μπορείτε να αντιμετωπίσετε καλύτερα το ποιο μπορεί να είναι το πρόβλημα. Για παράδειγμα, ένα σφάλμα 404 Not Found σημαίνει ότι το περιεχόμενο είτε δεν υπάρχει είτε έχει μετακινηθεί.  

## Τι είναι το HTTPS;  

Το HTTPS σημαίνει Hypertext Transfer Protocol Secure, (αναφέρεται επίσης ως HTTP μέσω TLS ή HTTP μέσω SSL).  Όταν εισάγουμε https:// στη γραμμή διευθύνσεων, λέμε στο πρόγραμμα περιήγησης να συνδεθεί μέσω HTTPS, να κάνει δηλαδή μία ασφαλή σύνδεση. Το HTTPS χρησιμοποιεί επίσης το TCP (Transmission Control Protocol) για την αποστολή και λήψη δεδομένων, αλλά το κάνει μέσω της θύρας 443. 

![]({{ site.baseurl }}/blog/assets/images/https.png)

Από τον Απρίλιο του 2016, το 41,7% των 141.160 πιο δημοφιλών ιστότοπων χρησιμοποιεί το HTTPS.

Το HTTPS μεταδίδει τα δεδομένα χρησιμοποιώντας μια κρυπτογραφημένη σύνδεση. Χρησιμοποιεί ένα δημόσιο κλειδί το οποίο στη συνέχεια αποκρυπτογραφείται απο τον παραλήπτη. Το δημόσιο κλειδί διατηρείτε στον διακομιστή και είναι μέρος του πιστοποιητικού SSL. Τα πιστοποιητικά υπογράφονται κρυπτογραφικά από μια Αρχή έκδοσης πιστοποιητικών (CA - Certificate Authority)    

Αν εξετάσουμε την κύρια διαφορά μεταξύ HTTP και HTTPS, το HTTPS έχει προφανώς ένα μεγάλο πλεονέκτημα. Τελικά, δεν θα θέλατε ο ιστότοπός σας να είναι όσο το δυνατόν πιο ασφαλής; 

Το θέμα είναι ότι εάν δεν έχετε κάποια σελίδα ηλεκτρονικού εμπορίου και δεν δέχεστε ευαίσθητες πληροφορίες από τους επισκέπτες του ιστότοπού σας, τότε μπορεί να νομίζετε ότι η μετάβαση σε έναν ιστότοπο HTTPS δεν είναι τόσο απαραίτητη και ότι είναι μεγαλύτερη ταλαιπωρία από όσο αξίζει.

Ωστόσο, τα πλεονέκτηματα ασφαλείας δεν είναι το μόνο πλεονέκτημα της χρήσης HTTPS. Στην πραγματικότητα, η μετάβαση στο HTTPS μπορεί να ενισχύσει και τις προσπάθειές σας στο SEO.     

Το HTTPS έχει πολλά πλεονεκτήματα, τόσο απόδοσης όσο και, το πιο σημαντικό, την ασφάλεια. Όλα τα προγράμματα περιήγησης ενθαρρύνουν έντονα τους χρήστες να εμπιστεύονται μόνο ιστότοπους που εφαρμόζουν HTTPS, επειδή αυτό είναι το μοναδικό μέτρο που μπορεί να τους βοηθήσει να μετριάσουν μια ποικιλία απειλών και επιθέσεων. 