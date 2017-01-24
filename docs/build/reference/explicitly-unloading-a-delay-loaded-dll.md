---
title: "遅延読み込みした DLL の明示的なアンロード | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY:UNLOAD リンカー オプション"
  - "__FUnloadDelayLoadedDLL2"
  - "DELAY:UNLOAD リンカー オプション"
  - "遅延読み込み (DLL を), アンロード"
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 遅延読み込みした DLL の明示的なアンロード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/delay](../../build/reference/delay-delay-load-import-settings.md):unload リンカー オプションによって、遅延読み込みした DLL をアンロードできます。  既定では、\/delay:unload と **\_\_FUnloadDelayLoadedDLL2** をコードに使用して DLL がアンロードされると、遅延読み込みされたインポートがインポート アドレス テーブル \(IAT: Import Address Table\) に残ります。  しかし、リンカーのコマンド ラインで \/delay:unload を指定した場合は、ヘルパー関数によって DLL の明示的アンロードがサポートされます。IAT は元の内容にリセットされ、無効になったポインターが上書きされます。  IAT は、元の IAT のコピーがある場合に、そのアドレスが格納される [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) のフィールドです。  
  
## 例  
  
### コード  
  
```  
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD  
#include <windows.h>  
#include <delayimp.h>  
#include "MyDll.h"  
#include <stdio.h>  
  
#pragma comment(lib, "delayimp")  
#pragma comment(lib, "MyDll")  
int main()  
{  
    BOOL TestReturn;  
    // MyDLL.DLL will load at this point  
    fnMyDll();  
  
    //MyDLL.dll will unload at this point  
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");  
  
    if (TestReturn)  
        printf_s("\nDLL was unloaded");  
    else  
        printf_s("\nDLL was not unloaded");  
}  
```  
  
### コメント  
 遅延読み込みされた DLL のアンロードに関する重要事項  
  
-   **\_\_FUnloadDelayLoadedDLL2** 関数の実装は、\\VC7\\INCLUDE\\DELAYHLP.CPP ファイルにあります。  
  
-   **\_\_FUnloadDelayLoadedDLL2** 関数の名前パラメーターは、大文字と小文字の区別も含めて、インポート ライブラリの内容と完全に一致している必要があります。文字列もイメージのインポート テーブルの内容と同じになります。  インポート ライブラリの内容は、[DUMPBIN \/DEPENDENTS](../Topic/-DEPENDENTS.md) で表示できます。  文字列の大文字と小文字を区別しない場合は、CRT 文字列関数のいずれかを使用するように、または Windows API 呼び出しを使用するように、**\_\_FUnloadDelayLoadedDLL2** を更新します。  
  
 詳細については、「[遅延読み込みした DLL のアンロード](../../build/reference/unloading-a-delay-loaded-dll.md)」を参照してください。  
  
## 参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)