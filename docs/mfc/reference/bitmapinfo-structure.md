---
title: "BITMAPINFO 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BITMAPINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAPINFO 構造体"
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# BITMAPINFO 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`BITMAPINFO` 構造体は、Windows のデバイスに依存しないビットマップ \(DIB: Device\-Independent Bitmap\) の寸法と色の情報を定義します。  
  
## 構文  
  
```  
typedef struct tagBITMAPINFO {  
   BITMAPINFOHEADER bmiHeader;  
   RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### パラメーター  
 `bmiHeader`  
 デバイスに依存しないビットマップの寸法とカラー フォーマットに関する情報を保持する [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) 構造体を指定します。  
  
 `bmiColors`  
 ビットマップの色を定義する [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) データ型または `DWORD` データ型の配列を指定します。  
  
## 解説  
 デバイスに依存しないビットマップは、2 つの異なる部分から構成されます。ビットマップの寸法と色を表す `BITMAPINFO` 構造体と、ビットマップのピクセルを指定するバイトの配列です。  配列内のビットはパックされますが、各スキャン ラインには `LONG` 境界上で終わるように 0 が埋め込まれている必要があります。  高さが正の値のとき、ビットマップの原点は左下隅になります。  高さが負の値のとき、原点は左上隅になります。  
  
 *パックされたビットマップ*は、バイト配列が `BITMAPINFO` 構造体の直後にあるビットマップです。  パックされたビットマップは、1 つのポインターで参照されます。  
  
 `BITMAPINFO` 構造体の詳細と、`BITMAPINFOHEADER` 構造体および `RGBQUAD` 構造体のメンバーの適切な値の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] ドキュメントで次のトピックを参照してください。  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="b5dd2e8c9cedbac12eb858bd01a029a2" class\="tgtSentence"\>BITMAPINFO 構造体\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
-   [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) 構造体  
  
-   [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 構造体  
  
## 必要条件  
 **ヘッダー :** wingdi.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)