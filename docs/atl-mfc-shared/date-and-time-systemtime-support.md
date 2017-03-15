---
title: "日付と時刻: SYSTEMTIME サポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "システム時刻"
  - "CTime クラスを使用して、FILETIME 構造体"
  - "書式設定時 [C++]"
  - "SYSTEMTIME 構造体"
  - "MFC の日付 [C++]"
  - "期間、書式指定 [C++]"
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 日付と時刻: SYSTEMTIME サポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

 [CTime](../Topic/CTime%20Class.md) クラスには、Win32 からシステムとファイルの時間を受け入れるコンス トラクターです。 このような目的に `CTime` オブジェクトを使用する場合は、この記事の説明に従って初期化を適宜変更する必要があります。  
  
 SYSTEMTIME 構造体については、次を参照してください。 [SYSTEMTIME](../mfc/reference/systemtime-structure1.md)します。 FILETIME 構造体については、次を参照してください。 [FILETIME](../mfc/reference/filetime-structure.md)します。  
  
 MFC では今でも MS-DOS スタイルの時間の引数を受け取る `CTime` コンストラクターが提供されていますが、MFC バージョン 3.0 からは、`CTime` クラスで、Win32 の `SYSTEMTIME` 構造体を受け取るコンストラクターと、Win32 の `FILETIME` 構造体を受け取る別のコンストラクターもサポートされています。  
  
 新しい `CTime` コンストラクターは、次のとおりです。  
  
-   CTime (const SYSTEMTIME & `sysTime`) です。  
  
-   CTime (const FILETIME & `fileTime`) です。  
  
 `fileTime` パラメーターは Win32 の `FILETIME` 構造体への参照で、この構造体は時間を 64 ビット値で表します。`SYSTEMTIME` 構造体よりも内部ストレージに便利な形式で、ファイルの作成時間を表すために Win32 で使用されます。  
  
 システム時刻で初期化された `CTime` オブジェクトがコードに含まれる場合は、Win32 の `SYSTEMTIME` コンストラクターを使用する必要があります。  
  
 多くの場合は使用しません `CTime` `FILETIME` 初期化を直接します。 使用する場合、 `CFile` ファイルを操作するオブジェクト [cfile::getstatus](../mfc/reference/cfile-class.md#getstatus) 経由でのファイルのタイムスタンプを取得、 `CTime` オブジェクトを初期化して、 `FILETIME` 構造体。  
  
## <a name="what-do-you-want-to-know-more-about"></a>方法については、クリックしてください。  
  
-   [MFC の一般的な日付と時刻](../atl-mfc-shared/date-and-time.md)  
  
-   [日付と時刻のオートメーションによるサポート](../Topic/Date%20and%20Time:%20Automation%20Support.md)  
  
-   [日付と時刻の汎用クラス](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>関連項目  
 [日付と時刻](../atl-mfc-shared/date-and-time.md)

