# Git Workflow
TBD.

## Branch Strategy
TBD.

## Commit
* Commit message:
  * Use PascalCase for feature name
  * Commit message using english
  * Use the feature name prefix
  * Example
    > FeatureName: message

## Pull/Merge Request
### Workflow
1. Saat membuat Pull Request (PR), buat deskripsi yang setidaknya mengandung hal-hal berikut:
  - Tujuan PR, misalnya implementasi fitur baru atau bugfix. Jika perlu, tambahkan screenshot atau tabel yang dapat membantu menjelaskan PR tersebut.
  - URL ke ticket yang membahas PR tersebut (jika tim menggunakan issue/task management tools).
2. Mention setidaknya satu anggota tim dan satu engineer di luar tim (biasanya tech lead).
3. Jika ada feedback untuk revisi kode, dan jika revisi sudah dilakukan, mention kembali pihak yang terlibat dalam diskusi feedback tersebut.
4. PR hanya dapat di-merge jika sudah di-approve oleh setidaknya satu anggota tim dan satu engineer di luar tim (biasanya tech lead).
5. Setelah source branch yang digunakan untuk PR berhasil di-merge ke target branch (misalnya branch `development`), hapus branch tersebut. Langkah ini tidak perlu dilakukan jika source branch yang digunakan adalah `development`, dan target branch adalah `master`.
### Catatan
- Ada setting yang dapat digunakan untuk menjadikan branch `development` dan `master` sebagai protected branch, mencegah branch tersebut agar tidak sengaja terhapus.
  - [Protected branch di GitHub](https://docs.github.com/en/github/administering-a-repository/about-protected-branches) (Saat ini tidak tersedia untuk private repo yang menggunakan GitHub Free plan)
  - [Protected branch di GitLab](https://docs.gitlab.com/ee/user/project/protected_branches.html)

## Code Review dan Approval
### Intro
Code review adalah proses di mana kode yang dibuat oleh seorang engineer di-review oleh engineer lainnya. Code review pada umumnya dilakukan sebelum feature branch di-merge ke target branch (`development` atau `master`).
Tujuan dari code review adalah:
- Meningkatkan code quality dengan cara memperbaiki code style dan memperbaiki bagian kode yang berpotensi menimbulkan bug
- Mendapatkan implementasi logic terbaik untuk menyelesaikan suatu masalah
- Meningkatkan code ownership di antara anggota tim, terutama jika setiap anggota tim mengerjakan fitur yang berbeda dan menggunakan file yang berbeda.
### Guideline untuk Code Author
TBD.
### Guideline untuk Reviewer
TBD.
### Referensi
- [Google Engineering Practices - How to do a code review](https://google.github.io/eng-practices/review/)

## Deployment
TBD.
