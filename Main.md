# Dependency Management Terminology

## Artifact
- Ám chỉ 1 file/folder được tạo ra nhờ build
  Example: file JAR, file ZIP hoặc **Native executable**
### Native executable là cái gì?
  - Nó liên quan tới 1 khái niệm lớn - Native Image
  - Về cơ bản, native executable là một file chỉ có mã nhị phân trong đó, một file thực thi trực tiếp trên hệ điều hành mà không cần phải chạy trong máy ảo Java (JVM)
>> Khi được thiết kế để user, hosting systems hoặc project khác dùng nó, hoặc để triển khai hosting systems - Artifact là 1 file duy nhất

>> Khi có dependencies giữa các project nhằm tránh chi phí tạo product có thể xuất bản - Artifact là Directories

# Capability:
- ám chỉ xác định một tính năng được cung cấp bởi 1 hoặc nhiều components
- 1 Capability được xác định bằng tọa độ GAV(group, artifact, version)
Ví dụ: 
```
plugins {
    id 'java'
}

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.jsoup:jsoup:1.14.3'
}
```
- GroupId: *org.jsoup*
- ArtifactId: *jsoup*
- Version: *1.14.3*
### Capability có thể được sử dụng để thể hiện rằng một thành phần cung cấp nhiều biến thể tính năng hoặc hai thành phần khác nhau triển khai cùng một tính năng (và do đó không thể sử dụng cùng nhau)
