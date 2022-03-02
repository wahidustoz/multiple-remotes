# Multiple Git Remotes

### `SSH Key`larni yaratish
1. terminal'da `~/.ssh` degan papkaga boramiz
2. papka ichida quyidagi kommandalar orqali `github` va `gitlab` uchun alohida `ssh key`lar yaratamiz. *Github va Gitlab email addresslarni to'ldirish esdan chiqmasin. Ular bir xil bo'lsa ham hechqisi yo'q :)* 
```sh
ssh-keygen -t rsa -C "your@github.email"
ssh-keygen -t rsa -C "your@gitLAB.email"
```
   2.1. `github` va `gitlab` emaillarini to'ldirish esdan chiqmasin
3. `~/.ssh` papkasi ichida `code config` komandasi orqali yangi **config** degan fayl yaratamiz va quyidagi kodlarni saqlaymiz
```sh
Host github.com
    Hostname github.com
    User git
    IdentityFile ~/.ssh/github

Host gitlab.com
    Hostname gitlab.com
    User git
    IdentityFile ~/.ssh/gitlab
```
4. **Github**ga kiring va *Settings > SSH and GPG keys*'ga borib **New SSH key** tugmasini bosing.
   3.1. **Title** degan joyiga *key* uchun istalgan nom bering.
   3.2. `~/.ssh` papkada hosil bo'lgan **github.pub** fayl ichidagi hamma tekstni ko'chiring va **Title** tagidagi *tekst maydon**ga tashlang. 
   3.3 **Add SSH Key** tugmasini bosing.
5. **GitLab**ga borib *Preferences > SSH Keys* sahifasiga boring.
   4.1. `~/.ssh` papkada hosil bo'lgan **gitlab.pub** fayl ichidagi hamma tekstni 
   4.2. **Key** degan *tekst maydon*ga yuqorida ko'chirilgan tekstni tashlang
   4.3. **Title** degan joyiga *key* uchun istalgan nom bering.
   4.4. *Expiration Date*ga shu **key** qachongacha ishlashi kerakligini tanlang. **1 yil keyingi sanani kiritish tavsiya qilinadi*
   4.5. **Add Key** tugmasini bosib yakunlang

Hammasi tayyor! Endi siz `git remote` qo'shishda **HTTPS** linklarni EMAS `SSH` linklarni qo'shishingiz kerak bo'ladi.
> Masalan: Tayyor repositoriyaga quyidagi kodlarni kiritsangiz, u github va gitlab'ga bir vaqtning o'zida kod yuklay oladi. 
```sh
git remote add github "github repo ssh link"
git remote add gitlab "gitlab repo ssh link"
```

