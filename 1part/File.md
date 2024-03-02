# Работа с файловой системой
1. [Работа с дисками]
2. Работа с каталогами
3. Работа с файлами


## 1. Работа с дисками
Для представления информации о диске в пространстве имен System.IO используется класс DriveInfo. В этом классе находится статический метод GetDrives(), который возвращает информацию обо всех логических дисках компьютера. Также DriveInfo предоставляет ряд полезных свойств:

- AvailableFreeSpace: указывает на объем доступного свободного места на диске в байтах доступного текущему пользователю
- DriveFormat: получает имя файловой системы
- DriveType: представляет тип диска
- IsReady: готов ли диск (например, DVD-диск может быть не вставлен в дисковод)
- Name: получает имя диска
- TotalFreeSpace: получает общий объем свободного места на диске в байтах доступного всем пользователям
- TotalSize: общий размер диска в байтах
- VolumeLabel: получает или устанавливает метку тома
- RootDirectory: возвращает информацию о корневом каталоге диска
Получим информацию обо всех дисках на компьютере:
```
using System;
using System.IO;
namespace FileSystem
{
    class Program
    {
        static void Main(string[] args)
        {
            DriveInfo[] drives = DriveInfo.GetDrives();
            foreach (DriveInfo drive in drives)
            {
                Console.WriteLine($"Название: {drive.Name}");
                Console.WriteLine($"Тип: {drive.DriveType}");
                if (drive.IsReady)
                {
                    Console.WriteLine($"Объем диска: {drive.TotalSize}");
                    Console.WriteLine($"Свободное пространство: {drive.TotalFreeSpace}");
                    Console.WriteLine($"Метка: {drive.VolumeLabel}");
                }
            }
        }
    }
}
```


## 2. Работа с каталогами

## 3. Работа с файлами
