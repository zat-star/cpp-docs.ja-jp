---
title: "メモリ管理 : ヒープ割り当て | Microsoft Docs"
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
  - "delete 演算子, 使用 (デバッグ MFC で)"
  - "検出 (メモリ リークを)"
  - "ヒープ割り当て"
  - "ヒープ割り当て, 記述済み"
  - "メモリの割り当て, ヒープ メモリ"
  - "メモリ リーク, 検出"
  - "メモリ, 検出 (リークを)"
  - "new 演算子, 使用 (デバッグ MFC で)"
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メモリ管理 : ヒープ割り当て
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヒープは、プログラムのメモリ割り当てのニーズに対応するために予約されています。  これは、プログラム コードとは別に、スタック領域です。  一般的な C プログラムはヒープ メモリの割り当てと解放するために関数 `malloc` と **free** を使用します。  MFC のデバッグ バージョンではヒープ メモリ オブジェクトの割り当てと解放するために C\+\+ の組み込み演算子の **new** と **delete** 変更バージョンが用意されています。  
  
 `malloc` と **free**の代わりに **new** と **delete** を使用すると、メモリ リークの検出に役立つクラスの場合は、クラス ライブラリのメモリ管理のデバッグの機能強化を利用できます。  MFC のリリース バージョンでプログラムをビルドする場合、**new** と **delete** の演算子の標準バージョンがメモリの割り当てと解放する効率的 \(MFC のリリース バージョンでは、これらの演算子の変更後のバージョンを提供しません\)。  
  
 ヒープに割り当てられたオブジェクトの合計サイズがシステムで使用できる仮想メモリだけが制限されることに注意してください。  
  
## 参照  
 [メモリ管理](../mfc/memory-management.md)