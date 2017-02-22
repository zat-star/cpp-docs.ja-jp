---
title: "BLOB の取得 | Microsoft Docs"
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
  - "BLOB (バイナリ ラージ オブジェクト), 取得"
  - "OLE DB, BLOB (バイナリ ラージ オブジェクト)"
  - "取得 (BLOB を)"
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB の取得
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バイナリ ラージ オブジェクト \(BLOB: Binary Large Object\) は、さまざまな方法で取得できます。  **DBTYPE\_BYTES** を使用して、BLOB をバイト シーケンスとして取得できます。または、`ISequentialStream` などのインターフェイスを使用できます。  詳細については、『OLE Programmer's Reference』の「[BLOBS and OLE Objects](https://msdn.microsoft.com/en-us/library/ms711511.aspx)」を参照してください。  
  
 以下のコードでは、`ISequentialStream` を使用して BLOB を取得する方法を示しています。  [BLOB\_ENTRY](../Topic/BLOB_ENTRY.md) マクロでは、インターフェイスと、インターフェイスに使用するフラグを指定できます。  テーブルを開いた後で、`ISequentialStream` に対して **Read** を繰り返し呼び出して、BLOB からバイトを読み込みます。  `MoveNext` を呼び出して次のレコードを取得する前に、**Release** を呼び出してインターフェイス ポインターを破棄します。  
  
```  
class CCategories  
{  
public:  
   ISequentialStream*   pPicture;  
  
BEGIN_COLUMN_MAP(CCategories)  
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CCategories> > categories;  
ULONG          cb;  
BYTE            myBuffer[65536];  
  
categories.Open(session, "Categories");  
while (categories.MoveNext() == S_OK)  
{  
   do  
   {  
      categories.pPicture->Read(myBuffer, 65536, &cb);  
      // Do something with the buffer  
   } while (cb > 0);  
   categories.pPicture->Release();  
}  
```  
  
 BLOB データを処理するマクロの詳細については、「[OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)」の「列マップ マクロ」を参照してください。  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)   
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)