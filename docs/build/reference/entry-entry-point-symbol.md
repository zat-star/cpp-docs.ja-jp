---
title: "/ENTRY (エントリ ポイント シンボル) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/entry"
  - "VC.Project.VCLinkerTool.EntryPointSymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ENTRY リンカー オプション"
  - "ENTRY リンカー オプション"
  - "-ENTRY リンカー オプション"
  - "開始アドレス"
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ENTRY (エントリ ポイント シンボル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ENTRY:function  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *機能性*  
 .exe ファイルまたは DLL に対してユーザーが定義した開始アドレスを指定する関数。  
  
## 解説  
 \/ENTRY オプションは、.exe ファイルまたは DLL の開始アドレスのエントリ ポイント関数を指定します。  
  
 指定する関数は、呼び出し規約 `__stdcall` で定義されている必要があります。  パラメーターと戻り値は、プログラムがコンソール アプリケーションか、Windows アプリケーションか、または DLL かによって異なります。  エントリ ポイントの設定は、リンカーに任せることをお勧めします。このようにすると、C のランタイム ライブラリが正確に初期化され、静的オブジェクト用の C\+\+ のコンストラクターが実行されます。  
  
 既定では、先頭アドレスは C のランタイム ライブラリ内の関数名になります。  リンカーは、プログラムの属性に応じて関数名を選択します。次の表は、関数名とそれに対応する既定のアプリケーションです。  
  
|関数名|既定|  
|---------|--------|  
|**mainCRTStartup** \(または **wmainCRTStartup**\)|\/SUBSYSTEM:**CONSOLE** を使ってビルドされたアプリケーション。**main** 関数 \(または **wmain** 関数\) を呼び出します。|  
|**WinMainCRTStartup** \(または **wWinMainCRTStartup**\)|\/SUBSYSTEM:**WINDOWS** を使ってビルドされたアプリケーション。`WinMain` 関数 \(または **wWinMain** 関数\) を呼び出します。この場合、WinMain \(または wWinMain\) は `__stdcall` で定義されている必要があります。|  
|**\_DllMainCRTStartup**|DLL ファイル。`DllMain` 関数がある場合は、この関数を呼び出します。この場合、DllMain は `__stdcall` で定義されている必要があります。|  
  
 [\/DLL](../../build/reference/dll-build-a-dll.md) オプションまたは [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) オプションを指定しない場合は、**main** または `WinMain` が定義されているかどうかに応じて、サブシステムおよびエントリ ポイントが選択されます。  
  
 **main** 関数、`WinMain` 関数、および `DllMain` 関数の 3 つの関数は、ユーザー定義のエントリ ポイントの形式です。  
  
 マネージ イメージを作成する場合は、\/ENTRY で指定された関数に、\(LPVOID *var1*, DWORD *var2*, LPVOID *var3*\) の署名が必要です。  
  
 独自の DllMain エントリ ポイントを定義する方法については、「[ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **\[詳細\]** プロパティ ページをクリックします。  
  
4.  \[エントリ ポイント\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)