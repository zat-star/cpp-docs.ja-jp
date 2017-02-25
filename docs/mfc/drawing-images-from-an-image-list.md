---
title: "イメージ リストのイメージの描画 | Microsoft Docs"
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
  - "CImageList クラス, 描画 (イメージを)"
  - "描画, イメージ (イメージ リストの)"
  - "イメージ リスト [C++], 描画 (イメージを)"
  - "イメージ [C++], 描画"
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# イメージ リストのイメージの描画
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージを描画するには、[CImageList::Draw](../Topic/CImageList::Draw.md) メンバー関数を使用します。  デバイス コンテキスト オブジェクトは、イメージのインデックスに描画するポインターをイメージを描画スタイルを示すために描画する、一連のフラグ デバイス コンテキストの場所を指定します。  
  
 `ILD_TRANSPARENT` のスタイルを指定すると、**描画** はマスクされたイメージを描画するために、二つの手順から成るプロセスを使用します。  まず、イメージの、ビット マスクのビットごとの論理 AND 演算を実行します。  その後、最初の操作の結果と先のデバイス コンテキストの Background ビットの論理 XOR 演算を実行します。  このプロセスは、結果のイメージの透明な領域を作成します; つまり、マスクの白いビットは結果のイメージの対応するビットが透明になります。  
  
 純色の背景のマスクされたイメージを描画する前に、配置先と同じ色にイメージ リストの背景色を設定するには [SetBkColor](../Topic/CImageList::SetBkColor.md) メンバー関数を使用する必要があります。  色を設定すると、イメージの透明な領域を作成する必要がなく、**描画** をパフォーマンスに大きな増加して、先のデバイス コンテキストにイメージをコピーできるようにします。  **描画**を呼び出すときにイメージを描画するには、`ILD_NORMAL` のスタイルを指定します。  
  
 すべての背景に正しく描画機能がマスクされたイメージ リスト \([CImageList](../Topic/CImageList%20Class.md)\) の背景色は、いつでも設定できます。  `CLR_NONE` に背景色を設定するには、イメージを透過的に既定で描画します。  イメージ リストの背景色を取得するには、[GetBkColor](../Topic/CImageList::GetBkColor.md) メンバー関数を使用します。  
  
 `ILD_BLEND25` と `ILD_BLEND50` のスタイルのディザー システムの強調表示色イメージ。  これらのスタイルは、ユーザーが選択できるオブジェクトを表すためにマスクされたイメージを使用する場合に便利です。  たとえば、ユーザーが選択すると、イメージの描画に `ILD_BLEND50` のスタイルを使用できます。  
  
 nonmasked イメージは **SRCCOPY** のラスター オペレーションを使用して先のデバイス コンテキストにコピーされます。  イメージの色は、デバイス コンテキストの背景色に関係なく同じように表示されます。  **描画** で指定された描画スタイルも nonmasked イメージの外観には影響しません。  
  
 描画のメンバー関数に加えて、もう一方は関数、[DrawIndirect](../Topic/CImageList::DrawIndirect.md)、イメージをレンダリングする機能を拡張します。  `DrawIndirect` は、パラメーターとして、[IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) 構造体を取得します。  この構造体がラスター オペレーション \(ROP\) のコードの使用を含む、現在のイメージの描画をカスタマイズするために使用できます。  ROP コードの詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [ラスター オペレーション操作符号](http://msdn.microsoft.com/library/windows/desktop/dd162892) と [ブラシとしてビットマップ](http://msdn.microsoft.com/library/windows/desktop/dd183378) を参照します。  
  
## 参照  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)