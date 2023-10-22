# Full project

<https://youtu.be/KxqlJblhzfI>

## Setup và chạy thử project lần đầu

### Đóng gói project

```base //
mvn clean install
```

### Chạy project

```base //
java -jar security-0.0.1-SNAPSHOT.jar
```

## User.java

<https://youtu.be/KxqlJblhzfI?t=1555>  

### Từ khóa Implements được sử dụng để thực hiện một interface

Trong file User.java:  

``` java //
 public class User implements UserDetails
```  

### Từ khóa Enum sử dụng để định nghĩa một kiểu dữ liệu , đại diện cho một tập hợp các hằng số cố định  

Trong file User.java:

``` java //
    @Enumerated(EnumType.STRING)
    private Role role;
```

@Enumerated là một annotation được sử dụng để đánh dấu một trường là kiểu enum khi lưu trữ trong cơ sở dữ liệu. Khi lưu trữ và đọc từ cơ sở dữ liệu, giá trị của trường enum sẽ được tự động chuyển đổi sang tên của Enum tương ứng.

### Phương thức getAuthorities  

Trong file User.java:

``` java //
    @Override
    public Collection<? extends GrantedAuthority> getAuthorities() {
        return List.of(new SimpleGrantedAuthority(role.name()));
    }
```

Lấy danh sách các quyền được cấp cho đối tượng Authentication.  

Kiểu trả về của phương thức này là một Collection chứa các đối tượng thuộc kiểu GrantedAuthority hoặc một lớp kế thừa từ GrantedAuthority (sử dụng ***Wildcard***).  

GrantedAuthority là một interface đại diện cho một quyền được cấp cho người dùng. Mỗi đối tượng GrantedAuthority chứa một chuỗi đại diện cho một quyền cụ thể, chẳng hạn như ROLE_ADMIN hoặc ROLE_USER. Spring Security sử dụng danh sách các quyền này để kiểm tra xem người dùng có được phép truy cập vào tài nguyên được bảo vệ hay không.  

SimpleGrantedAuthority là một lớp cơ bản trong Spring Security, được sử dụng để lưu trữ một chuỗi đại diện cho một quyền được cấp cho đối tượng Authentication.  

## UserRepository.java  

<https://www.youtube.com/watch?v=KxqlJblhzfI&t=1499s>  

## 

<https://youtu.be/KxqlJblhzfI?t=2504>  


mvn run 