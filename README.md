# AutoLDPlayerNCT
Auto ADB LDPlayer
Release Bao Gồm
- ldconsole.exe
- Emgu.CV.World.dll
- LDController.dll


# List Command
0. Set Path LDPlayer "ldconsole.exe"
```js
    LDController.pathLD = "Your Path ldconsole.exe"; //VD: "C:\LDPlayer\LDPlayer4.0\ldconsole.exe"
```

1. Initialization
```js
   using LDPlayerNTC;
```

2. Manipulation Emulator
```js
    void Open(string param, string NameOrId)
    void Open_App(string param, string NameOrId, string Package_Name) //Mở LD cùng app khi chạy
    void Close(string param, string NameOrId)
    void CloseAll()
    void ReBoot(string param, string NameOrId)
```
```js
    Exam:   ldplayer.Open("name", "ld0");
            ldplayer.Open("index", "0");
```
3. Custom Emulator
```js
void Create(string Name)
void Copy(string Name, string From_NameOrId)
void Delete(string param, string NameOrId)
void ReName(string param, string NameOrId, string title_new)
```

4. App 
```js
void InstallApp_File(string param, string NameOrId, string File_Name) //File_Name trỏ tới file apk
void InstallApp_Package(string param, string NameOrId, string Package_Name) //Cài qua LD Store, hơi dỏm, tốt nhất tự cài apk
void UnInstallApp(string param, string NameOrId, string Package_Name)
void RunApp(string param, string NameOrId, string Package_Name)
void KillApp(string param, string NameOrId, string Package_Name)
```

5. Orther
```js
void Locate(string param, string NameOrId, string Lng, string Lat) //Set Toạ Độ GPS
```

```js
void Change_Property(string param, string NameOrId, string cmd)
    cmd use: 
    [--resolution ]
    [--cpu < 1 | 2 | 3 | 4 >]
    [--memory < 512 | 1024 | 2048 | 4096 | 8192 >]
    [--manufacturer asus]
    [--model ASUS_Z00DUO]
    [--pnumber 13812345678]
    [--imei ]
    [--imsi ]    
    [--simserial ]
    [--androidid ]
    [--mac ]
    [--autorotate < 1 | 0 >]
    [--lockwindow < 1 | 0 >]
    Exam:   ldplayer.Change_Property("name", "ld0", " --cpu 1 --memory 1024 --imei 123456789");
```
```js
string ADB(string param, string NameOrId, string cmd))
void Backup(string param, string NameOrId, string file_path)
void Restore(string param, string NameOrId, string file_path)
void Pull(string param, string NameOrId, string remote_file_path, string local_file_path)
void Push(string param, string NameOrId, string remote_file_path, string local_file_path)
```
```js
void Golabal_Config(string param, string NameOrId, string fps, string audio, string fast_play, string clean_mode)
    [--fps <0~60>] [--audio <1 | 0>] [--fastplay <1 | 0>] [--cleanmode <1 | 0>]
    Exam: ldplayer.Golabal_Config("name", "ld0", "60", "0", "0", "0");
```
5. Get List Devices
```js
List<string> GetDevices()
List<string> GetDevices_Running()
bool IsDevice_Running(string param, string NameOrId)
List<Info_Devices> GetDevices2()
List<Info_Devices> GetDevices2_Running()
string GetNameOrIndex(string param, string NameOrIndex)
bool IsDevice_Running(string param, string NameOrIndex)
```

6. Cmd
```js
void ExecuteLD(string cmd)
string ExecuteLD_Result(string cmdCommand)
```

7. Rewrite KAutoHelper
```js
void Delay(double delayTime)
Point GetScreenResolution(string param, string NameOrIndex)
void TapByPercent(string param, string NameOrIndex, double x, double y, int count = 1)
void Tap(string param, string NameOrIndex, int x, int y, int count = 1)
void Key(string param, string NameOrIndex, ADBKeyEvent key)
void InputText(string param, string NameOrIndex, string text)
void SwipeByPercent(string param, string NameOrIndex, double x1, double y1, double x2, double y2, int duration = 100)
void Swipe(string param, string NameOrIndex, int x1, int y1, int x2, int y2, int duration = 100)
void PlanModeON(string param, string NameOrIndex, CancellationToken cancellationToken)
void PlanModeOFF(string param, string NameOrIndex, CancellationToken cancellationToken)
void LongPress(string param, string NameOrIndex, int x, int y, int duration = 100)
Bitmap ScreenShoot(string param, string NameOrIndex, bool isDeleteImageAfterCapture = true, string fileName = "screenShoot.png")
bool FindImage(string param, string NameOrIndex, string pathPNG)
Point? FindImageOutPoint(string param, string NameOrIndex, string pathPNG)
void addProxy(string param, string NameOrIndex, string ip, string port)
void removeProxy(string param, string NameOrIndex)
```
