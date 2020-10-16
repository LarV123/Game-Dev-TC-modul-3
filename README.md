# Game-Dev-TC-modul-3
Modul 3 Komunitas Game Dev TC 2020

## Tujuan
1. Peserta memahami basics 2D unity
2. Peserta dapat menggambarkan object dengan ```sprite renderer```
3. Peserta dapat menggunakan physics engine dalam unity
4. Peserta dapat membuat kontrol platformer sederhana

## Membuat platform Game

### Meng-import sprites

1. Download folder sprites dalam github ini.
![img](sprites/player.png)
![img](sprites/player_leg.png)
![img](sprites/tilemap.png)

Sprite - sprite tersebut akan menjadi asset graphic dalam game ini.

2. Setelah mendownload folder sprite, silahkan membuat project dengan setting 2D dan ubah nama project menjadi nama game (disini akan dinamai "platformer game").

![img](img/project_setup.png)

3. Masukkan folder sprite tersebut dalam projectnya, untuk mendapatkan direktory project dengan mudah. Dapat klik kanan dalam tab project lalu pilih Show in explorer.

![img](img/project_dir_show.png)

4. Karena game kita adalah game, pixel art, maka kita perlu setting gambarnya agar tidak ada anti-aliasing. Lalu karena semua gambar tersebut adalah sprite-sheet, maka kita harus memisahkannya menjadi individual sprite.
Klik gambar pada folder, maka inspector akan menunjukkan informasi berikut.

![img](img/sprite_inspector.png)

Ubah sprite mode menjadi multiple, dan pixel per unit menjadi 32. filter mode menjadi point, dan ubah format compression menjadi rgba32.

![img](img/sprite_good_setting.png)

Setelah itu klik apply.

5. Tekan sprite editor dalam inspector untuk memotong sprite tersebut. Maka akan keluar window seperti berikut

![img](img/sprite_editor.png)

Setelah itu, tekan slice dan ubah type ke ```Grid By Cell Size``` dan ubah x dan y menjadi 32. Lalu tekan slice.

![img](img/sprite_editor_2.png)

6. Lakukan hal tersebut pada sprite yang lainnya.

### Menggunakan Rigidbody2D dan Collider2D

1. Buat empty game object dan beri nama Player. Lalu buat 1 empty game object sebagai child object player dan beri nama "Graphic". Lalu buat 2 empty game object sebagai child object Graphic dan beri nama masing-masing "upper body" dan "lower body".

![img](img/player_hierarchy.png)

2. Beri Sprite Renderer pada upper body dan lower body. Pada upper body, beri sprite ```player_0``` sedangkan pada lower body, beri sprite ```player_leg_0```.

Attribut sprite adalah apa yang akan ditampilkan oleh sprite renderer. Dalam sprite renderer terdapat attribut lainnya seperti color. Color berfungsi untuk memberikan efek tint pada sprite.

![img](img/upper_body_sprite_renderer.png)

![img](img/lower_body_sprite_renderer.png)

Dalam scene akan terlihat seperti ini

![img](img/player_scene.png)

3. Dalam object Player tambahkan 2 component, yaitu Rigidbody2D dan BoxCollider2D.

Rigidbody2D digunakan untuk membuat object tersebut disimulasikan dalam physics engine unity. Dalam attributnya kita bisa memberikan body type.
Body type dalam Physics engine 2D ada 3, yaitu static, kinematic, dan dynamic.
- static berarti object akan dianggap sebagai benda yang tidak bergerak sama sekali.
- kinematic berarti object tersebut tidak akan digerakkan oleh physics engine unity, namun bisa digerakkan melalui script.
- dynamic berarti object akan digerakkan secara penuh oleh physics engine unity. Meskipun begitu, kita tetap dapat mengatur properti seperti kecepatan ataupun langsung mengubah posisi tersebut.

BoxCollider2D adalah salah satu collider primitive yang disediakan oleh unity. Collider adalah cara game mendeteksi pertabrakan benda. BoxCollider2D menandakan bahwa area dalam box itu adalah solid ke Rigidbody2D. Unity mempunyai collider lainnya, seperti :
- BoxCollider2D
- CircleCollider2D
- PolygonCollider2D
- CompositeCollider2D
- CapsuleCollider2D
- CircleCollider2D
- TilemapCollider2D

![img](img/player_inspector.png)

4. Edit box collider dengan menekan tombol ```edit collider``` pada inspector.

![img](img/edit_collider.png)

Lalu adjust box dalam player agar sesuai dengan graphic player.

![img](img/edited_collider_box.png)

5. Untuk ground, sementara kita dapat menggunakan sprite box. Kita akan belajar tile map di pelajaran selanjutnya. Unity menyediakan primitive sprite. Primitive sprite yang disediakan unity ada 6, yaitu Square, Triangle, Diamon, Hexagon, Circle, dan Polygon.

![img](img/primitive_sprite.png)

Buatlah sprite square, dan beri nama "Square".

6. Salah satu cara untuk membuat game object dengan sprite renderer, adalah dengan langsung men-drag and drop sprite ke scene view. Drag and drop sprite square langsung ke scene view, maka akan terbuat game object bernama square dengan gambar square.

![img](img/square_scene_view.png)

7. Ini akan menjadi ground sementara kita. Adjust besar ground tersebut agar pemain bisa bergerak bebas. Lalu tambahkan BoxCollider2D agar pemain kita tidak tembus ke tanah.

![img](img/ground_added.png)

8. Sekarang gamenya sudah bisa kita play, dan player akan collide dengan ground.

### Membuat kontrol platformer

1. Selanjutnya, kita akan buat agar player bisa bergerak dengan input keyboard. Buatlah script bernama, PlayerMovement.cs dan isi dengan kode berikut.

```

```

## References

https://docs.unity3d.com/Manual/Sprites.html
https://docs.unity3d.com/Manual/class-SpriteRenderer.html
https://docs.unity3d.com/Manual/Collider2D.html
https://docs.unity3d.com/Manual/class-Rigidbody2D.html
