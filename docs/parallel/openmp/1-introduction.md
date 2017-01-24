---
title: "1. Introduction | Microsoft Docs"
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
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1. Introduction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここではC および C\+\+ プログラムで共有メモリの並列化を指定するために使用できるコンパイラ ディレクティブライブラリ関数と環境変数のコレクションを指定します。  ここで説明する機能は*OpenMP C\/C\+\+ アプリケーション プログラミング インターフェイス*  として知られています \(API\)。  この特定の目的は販売元からの共有メモリのアーキテクチャでは汎用性のあるためプログラムに同時実行プログラミング モデルを提供することです。  OpenMP C\/C\+\+ API は多数の販売元からコンパイラによってサポートされます。  OpenMP の詳細については*OpenMP FORTRAN アプリケーション プログラミング インターフェイス*  が次の Web サイトでを検索する場合 :  
  
 移植性を許可している間このドキュメントで定義されたディレクティブライブラリ関数と環境変数はユーザーが並列プログラムを作成して管理することができます。  ディレクティブは一つのプログラムで複数のデータ構造体を含む C および C\+\+ の逐次プログラミング モデル \(SPMD\) 拡張して構造体および同期コンストラクトを共有する作業および私有化データの共有をサポートします。  OpenMP の C をサポートしC\+\+ をアクティブ OpenMP のすべてのコンパイラ ディレクティブの解釈を API にコンパイラ コマンド ライン オプションを含むコンパイラが可能になります。