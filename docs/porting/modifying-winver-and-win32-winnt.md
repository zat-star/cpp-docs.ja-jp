---
title: "WINVER および _WIN32_WINNT の変更 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_WIN32_WINNT in an upgraded Visual C++ project"
  - "WINVER in an upgraded Visual C++ project"
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# WINVER および _WIN32_WINNT の変更
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、Windows 95、Windows 98、Windows ME、Windows NT、および Windows 2000 がサポート対象外になりました。**WINVER** マクロまたは **\_WIN32\_WINNT** マクロをこれらのいずれかのバージョンの Windows に割り当てている場合は、そのマクロを修正する必要があります。 Visual C\+\+ の以前のバージョンを使用して作成したプロジェクトをアップグレードすると、**WINVER** マクロまたは **\_WIN32\_WINNT** マクロがサポート対象外になった Windows のバージョンに割り当てられている場合には、そのマクロに関連するコンパイル エラーが発生することがあります。  
  
## コメント  
 マクロを変更するには、ヘッダー ファイル \(たとえば、Windows を対象とするプロジェクトを作成するときに含まれる targetver.h\) で、以下の行を追加します。  
  
```  
#define WINVER 0x0A00 #define _WIN32_WINNT 0x0A00  
```  
  
 これは、Windows 10 オペレーティング システムを対象としています。 これらの値は、各 Windows バージョンのマクロを定義する Windows ヘッダー ファイル SDKDDKVer.h にもリストされています。 SDKDDKVer.h を含める前に、\#define ステートメントを追加する必要があります。 Windows の各バージョンの値をエンコードする、SDKDDKVer.h の Windows 10 バージョンの行を次に示します。  
  
```  
// // _WIN32_WINNT version constants // #define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0 #define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000 #define _WIN32_WINNT_WINXP                  0x0501 // Windows XP #define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003 #define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista #define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista #define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008 #define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista #define _WIN32_WINNT_WIN7                   0x0601 // Windows 7 #define _WIN32_WINNT_WIN8                   0x0602 // Windows 8 #define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1 #define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10 #define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10  
```  
  
 表示している SDKDDKVer.h のコピーに Windows のすべてのバージョンがリストされていない場合、古いバージョンの Windows SDK を使用している可能性があります。 既定では、[!INCLUDE[vs_dev14](../mfc/includes/vs_dev14_md.md)] の Win32 プロジェクトは Windows 8.1 SDK を使用します。 Windows 10 SDK を使用するには、[方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md) をご覧ください。  
  
> [!NOTE]
>  アプリケーションに内部 MFC ヘッダーを含めた場合には、値が動作する保証はありません。  
  
 **\/D** コンパイラ オプションを使用して、このマクロを定義することもできます。 詳細については、「[\/D \(プリプロセッサの定義\)](../build/reference/d-preprocessor-definitions.md)」を参照してください。  
  
 これらのマクロの意味について詳しくは、「[Windows ヘッダーの使用](http://msdn.microsoft.com/library/windows/desktop/aa383745)」をご覧ください。  
  
## 参照  
 [前の製品の変更点](http://msdn.microsoft.com/ja-jp/91fa1713-0778-4b6b-82f7-0fe0a23ab1db)