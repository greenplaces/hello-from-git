` mkdir hello-from-git`

` git init `

# สร้างไฟล์ชื่อ file1
` code file1 `
  เพิ่ม Hello World form git

` git status `
 #   คำสั่ง git status ใช้เพื่อแสดงสถานะของ working directory และ staging area ใน Git repository โดยจะแสดงข้อมูลเกี่ยวกับไฟล์ที่มีการเปลี่ยนแปลงแต่ยังไม่ได้ staged, ไฟล์ที่ถูก staged แต่ยังไม่ได้ commit, และไฟล์ที่ไม่ได้ถูกติดตาม (untracked files)

#  ผลลัพธ์
  No commits yet
    Untracked files:
    (use "git add <file>..." to include in what will be committed)
            Read-Git.md
            file1

 ` git add file1 `
 ` git status `
    Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
        มีการเพิ่ม -->   new file:   file1  

 ` git log ` 
 # :: ผลลัพธ์ ::
  error
  fatal: your current branch 'main' does not have any commits yet
  `  git commit file1 -m "Our very first commit 1"  ` 

   ` git log ` 
   คำสั่ง git log ใช้สำหรับแสดงประวัติการ commit ใน Git repository โดยจะแสดงรายการ commit ที่เกิดขึ้นเรียงตามลำดับเวลาย้อนหลัง
    :: ผลลัพธ์ ::
   commit 794fafc664b36eaa50af522e9fe6904c8820f3da (HEAD -> main)
    Author: John Doe <thongchai.te@invitracehealth.com>
    Date:   Tue Jul 23 18:49:03 2024 +0700

    กด q เพื่อ ออก 

  #  create repository ที่ github ชื่อ hello-from-git
  #  run command
  `    git remote add origin https://github.com/greenplaces/hello-from-git.git   ` 
  `    git branch -M main   ` 
  `    git push -u origin main   ` 
  #   ผลลัพธ์  
  #      Enumerating objects: 3, done.
  #       Counting objects: 100% (3/3), done.
  #       Writing objects: 100% (3/3), 246 bytes | 246.00 KiB/s, done.
  #       Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
  #       To https://github.com/greenplaces/hello-from-git.git
  #       * [new branch]      main -> main
  #       branch 'main' set up to track 'origin/main'.


# ---------------------------------------------------------------------
# ---------------  lesson 22 Comparing Files --------------------------

    git diff --staged

# add text to file1
  Git is better with GitHub
  Learn Giot. andAWS to git a great job

# run command
  git diff
   #   ผลลัพธ์
diff --git a/file1 b/file1
# แสดงว่าเรากำลังเปรียบเทียบไฟล์ `file1` ในสองสถานะที่ต่างกัน

        index 0f37073..0c9450d 100644
        # `index` บรรทัดนี้แสดงค่า hash ของไฟล์ทั้งสองสถานะ และค่าความเหมือนของไฟล์
        # ค่า `100644` แสดงสิทธิ์การเข้าถึงของไฟล์ในรูปแบบ Unix

        --- a/file1
        # แสดงไฟล์สถานะเก่า (`a/file1`)

        +++ b/file1
        # แสดงไฟล์สถานะใหม่ (`b/file1`)

        @@ -1 +1,3 @@
        # บรรทัดนี้แสดงว่าการเปลี่ยนแปลงเกิดขึ้นที่บรรทัดที่ 1
        # ในไฟล์เก่ามี 1 บรรทัด ในไฟล์ใหม่มี 3 บรรทัด

        -Hello World form git
        # บรรทัดนี้ถูกลบออกไป

        \ No newline at end of file
        # หมายเหตุ: ไม่มีบรรทัดว่างที่ท้ายไฟล์

        +Hello World form git
        # บรรทัดนี้ถูกเพิ่มเข้ามา (เหมือนกับบรรทัดเดิม แต่ถูกเพิ่มกลับเข้ามาในไฟล์ใหม่)

        +Git is better with GitHub
        # บรรทัดนี้ถูกเพิ่มเข้ามาในไฟล์ใหม่
# run command 
    git add .

   #  -------------------------- ผลลัพธ์    -------------------------- 
   # ใช้เพื่อเพิ่มไฟล์หรือการเปลี่ยนแปลงในไฟล์ไปยัง staging area 
   git diff --staged

    new file mode 100644
   # ระบุว่าไฟล์ `Read-Git.md` เป็นไฟล์ใหม่และมีสิทธิ์การเข้าถึงเป็น `100644` (ไฟล์ธรรมดาที่อ่าน-เขียนได้สำหรับเจ้าของ และอ่านได้สำหรับผู้อื่น)

    index 0000000..3399983
# `index` บรรทัดนี้แสดงค่า hash ของไฟล์ (จาก `0000000` ซึ่งหมายถึงไม่มีไฟล์ก่อนหน้า ไปยัง `3399983` ซึ่งเป็น hash ของไฟล์ใหม่)

--- /dev/null
# ไฟล์เก่าไม่มี (เพราะเป็นไฟล์ใหม่)

+++ b/Read-Git.md
# ไฟล์ใหม่ชื่อ `Read-Git.md` ถูกเพิ่มเข้ามา

@@ -0,0 +1,96 @@
# บรรทัดนี้แสดงว่ามีการเพิ่มเนื้อหาใหม่ในไฟล์ `Read-Git.md` ทั้งหมด 96 บรรทัด

+` mkdir hello-from-git`
# เพิ่มบรรทัดนี้ในไฟล์ใหม่ เป็นคำสั่งในการสร้างไดเรกทอรีใหม่ชื่อ `hello-from-git`

+` git init `
# เพิ่มบรรทัดนี้ในไฟล์ใหม่ เป็นคำสั่งในการเริ่มต้น Git repository ในไดเรกทอรีปัจจุบัน



# เพิ่มไฟล์ใหม่เข้าไป
  code file2
  git add .
  git diff --staged
   #  -------------------------- ผลลัพธ์    -------------------------- 
 
    new file mode 100644
 
index 0000000..a5a48f0
# `index` แสดงค่า hash ของไฟล์ในสองสถานะ: 
# `0000000` หมายถึงไฟล์เก่าที่ไม่มี (เพราะเป็นไฟล์ใหม่) 
# `a5a48f0` เป็นค่า hash ของไฟล์ใหม่ที่ถูกเพิ่มเข้ามา
--- /dev/null
# ไฟล์เก่าไม่เคยมี (เนื่องจากเป็นไฟล์ใหม่)
@@ -0,0 +1,129 @@
# บรรทัด @@ -0,0 +1,129 @@ ที่ปรากฏในผลลัพธ์ของคำสั่ง git diff ใช้ในการระบุส่วนที่มีการเปลี่ยนแปลงในไฟล์ โดยเฉพาะเมื่อไฟล์ใหม่ถูกเพิ่มเข้ามาหรือเมื่อมีการเปลี่ยนแปลงหลายบรรทัดในไฟล์
 

# run code
  git commit -m "added new file" 
# ไปที่ github.com copy link ที่ git clone