---
title: "入出力の代替手段 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56b7268083239fbec6b1744e1905e100fc357cc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="inputoutput-alternatives"></a>入出力の代替手段
Visual C++ には、入出力のプログラミングのいくつかの代替手段が用意されています。  
  
-   C ランタイム ライブラリの直接的なバッファーされない入出力。  
  
-   ANSI C ランタイム ライブラリのストリーム入出力。  
  
-   コンソールおよびポートの直接入出力。  
  
-   Microsoft Foundation Class ライブラリ。  
  
-   Microsoft C++ 標準ライブラリ。  
  
 iostream クラスは、バッファーされた書式設定テキストの入出力に役立ちます。 C++ プログラミング インターフェイスが必要であり、Microsoft Foundation Class (MFC) ライブラリを使用しない場合のバッファーされていない入出力またはバイナリ入出力にも役立ちます。 iostream クラスは、C ランタイム関数のオブジェクト指向の入出力の代替手段です。  
  
 iostream クラスは、Microsoft Windows オペレーティング システムで使用できます。 文字列とファイルのストリームは制限なしで動作しますが、文字モード ストリーム オブジェクト `cin`、`cout`、`cerr`、および `clog` には Windows グラフィカル ユーザー インターフェイスとの一貫性がありません。 また、Windows 環境と直接やり取りするカスタム ストリーム クラスを派生させることもできます。  
  
## <a name="see-also"></a>参照  
 [ストリームとは何か](../standard-library/what-a-stream-is.md)

