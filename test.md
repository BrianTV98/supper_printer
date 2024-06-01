# Mutilanguage

#### Phạm vi áp dụng.
- Toàn project.
#### Các folder và tệp tin liên quan.
- l10n.yaml
  *Tệp tin cấu hình ngôn ngũ*
- pubspect.yaml.
  *Cấu hình auto gen translate language*
- lib/translate /
> Hệ thống sẽ lấy tập tin en.arb là tập tin gốc, trong trường hợp  các file  transla te khác
> chưa có thì hệ thống sẽ tự động trả về  dữ liệu ở tập tin góc này.
> Vì vậy tuyệt đối không xoá tệp tin này trong mọi tình huống.

#### Technical và các thư viện phụ thuộc
*Được setup dặ trên recommend trên document của flutter. Chiụ  tác động mạnh mẽ của
gói thư viện ```intl```. Khó hoặc không tương thích với ```flutter_gen``` (tính đến thời điểm setup)*

#### Thêm từ mới.
1. Cơ chế  
   *Thêm đầy đủ các cặp ngôn ngữ vào file  các file arb, trường hợp  ngôn nngữ bị thiếu s trong file arb sẽ trả về ngôn ngữ ở tệp tin gốc*.
   *Hot Reload để flutter gen ra các file và dữ liệu cần  thiết*
2. Quy ước.
   [Modulen name|Tên viết tắt]_[key word]
3. Cách sử dụng.
   ```
        context.language.[keywork]
   ```

#### Thêm ngôn ngữ mới
1. Add language support tại ```MaterialApp```  (InitApp)
2. Add user interface tại   ```LanguageCubit```
3. Thêm mới file arb (file data) cho language đó  tại  ```lib\translate```
   *Ghi chú: Quy ước [locale].arb*
#### Xử lý trường "single noun" và "plural noun"

#### Xử lý trường hợp root code, dữ liệu  của một số  ngôn ngữ bị mất sau nhiều dời dev.
    => compare key với tệp tin góc xem thử có thiếu key ko? 
#### Các vấn đề liên quan đến hight scalable
=> Không app dụng, muốn hight scalable cần gỡ bỏ code gen và xyử lý tay toàn bộ. Đưa  các  tệp  file về từng nhóm theo module.

### Một số vấn đề khác
1. Trường hợp HotReload bằng button trên android studio không tự gen code.
   => Hot reload bằng cml: ```r``` enter 

