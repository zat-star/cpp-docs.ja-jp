---
title: "インターネット アプリケーションのテスト | Microsoft Docs"
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
  - "デバッグ [MFC], Web アプリケーション"
  - "デバッグ (Web アプリケーションを), テスト (アプリケーションを)"
  - "インターネットのデバッグとテスト"
  - "テスト, インターネット アプリケーション"
  - "Web アプリケーション, テスト"
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# インターネット アプリケーションのテスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Web サーバーで実行されるアプリケーションのインターネットになる一意のテストの問題があります。  最初のテストはサーバーに接続するシングルユーザ クライアントを使用して生成されます。  これにより、コードをデバッグするときに便利です。  
  
 また、実際の条件でテストする場合: モデム接続を含む高速接続、低速シリアル行に接続して複数のクライアントが。  実際の条件をシミュレートすることが困難な場合もありますが、使用可能なシナリオをデザインし、実行時により確実に価値があります。  可能であれば、容量を実行し、テストに重点を置くのツールを使用する必要があります。  バグの一部のクラスでは、タイミングのバグなど、見つけにくく、再生が困難です。  
  
 インターネット プログラミングの問題の 1 つが表示されます。  サイトへのアクセスは、サーバーが低下することがあります。  サーバーに適切に低下するだけです。  レジストリまたはクッキーに記述中にクライアントで記述中に\) アプリケーションが失敗すると、ユーザーのコンピューターに有害なできる何もしない場合 \(たとえば、データの破損が発生します。  
  
## 参照  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)