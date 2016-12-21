---
title: "C ランタイム エラー R6025 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6025"
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C ランタイム エラー R6025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pure virtual function call  
  
 純粋仮想関数の呼び出しを処理するためのオブジェクトのインスタンスが生成されていません。  
  
 アプリケーションでこのエラーが表示された場合は、アプリケーションのテクニカル サポートにお問い合わせください。  
  
 このエラーは、派生クラス型へのキャストによって作成されたポインター \(実際は基本クラスを指すポインター\) を使って抽象基本クラス中の仮想関数が呼び出されたときに発生します。  また、基本クラスの構築時に生成された **void\*** からクラスのポインターへのキャストが行われたときにも発生します。  
  
 詳細については、サイトを [マイクロソフトのサポート](http://go.microsoft.com/fwlink/?LinkId=75220) 参照します。