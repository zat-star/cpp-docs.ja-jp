---
title: "BITMAP 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BITMAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAP 構造体"
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# BITMAP 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**BITMAP** 構造体は、論理ビットマップの高さ、幅、カラー形式およびビット値を定義します。  
  
## 構文  
  
```  
  
      typedef struct tagBITMAP {  /* bm */  
   int bmType;  
   int bmWidth;  
   int bmHeight;  
   int bmWidthBytes;  
   BYTE bmPlanes;  
   BYTE bmBitsPixel;  
   LPVOID bmBits;  
} BITMAP;  
```  
  
#### パラメーター  
 *bmType*  
 ビットマップの種類を指定します。  論理ビットマップの場合、このメンバーは 0 であることが必要です。  
  
 *bmWidth*  
 ビットマップの幅 \(ピクセル単位\) を指定します。  幅は 0 より大きい値でなければなりません。  
  
 *bmHeight*  
 ラスター行数を使用してビットマップの高さを指定します。  高さは 0 より大きい値でなければなりません。  
  
 *bmWidthBytes*  
 各ラスター行に含まれるバイト数を指定します。  グラフィック デバイス インターフェイス \(GDI\) は、ビットマップ形式のビット値が整数値 \(2 バイト\) の配列を形成することを想定するため、この値は偶数であることが必要です。  つまり、**bmWidthBytes** \* 8 の値は、**bmWidth** メンバーと **bmBitsPixel** メンバーを掛けたときに得られる値と同じかそれより大きい、すぐ上にある 16 の倍数であることが必要です。  
  
 *bmPlanes*  
 ビットマップ内でのカラー プレーンの数を指定します。  
  
 *bmBitsPixel*  
 ピクセルを定義するために必要とされる各プレーンで、隣接するカラー ビット数を指定します。  
  
 *bmBits*  
 ビットマップのビット値が配置されている位置へのポインター。  **bmBits** メンバーは、1 バイト値から成る配列への long ポインターであることが必要です。  
  
## 解説  
 現在使用されているビットマップ形式は、モノクロおよびカラーです。  モノクロ ビットマップは、1 ビット、1 プレーンのファイル形式を使用します。  各スキャンは 16 ビットの倍数です。  
  
 スキャンは、次のように高さ *n* のモノクロ ビットマップとして編成されます。  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 モノクロ デバイス上のピクセルは黒と白のどちらかです。  ビットマップ内で対応するビットが 1 の場合、そのピクセルはオン \(白\) になります。  ビットマップ内で対応するビットが 0 の場合、そのピクセルはオフ \(黒\) になります。  
  
 すべてのデバイスは、[CDC::GetDeviceCaps](../Topic/CDC::GetDeviceCaps.md) メンバー関数の **RASTERCAPS** インデックス内で **RC\_BITBLT** ビットが設定 \(セット\) されているビットマップをサポートします。  
  
 各デバイスには、独自のカラー形式があります。  あるデバイスから他のデバイスにビットマップを転送するには、[GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) および [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) の各 Windows 関数を使用します。  
  
## 必要条件  
 **ヘッダー :** wingdi.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)