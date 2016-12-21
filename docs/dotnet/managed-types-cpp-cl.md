---
title: "マネージ型 (C++/CL) | Microsoft Docs"
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
  - "__gc 型"
  - "型 [C++], CLR"
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# マネージ型 (C++/CL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マネージ型の宣言の構文、およびマネージ型のオブジェクトの作成と使用は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から大幅に変更されています。  この変更は、ISO\-C\+\+ 型システム内での統合を促進するためのものです。  これらの変更について、次のサブセクションで詳しく説明します。  
  
## このセクションの内容  
 [マネージ クラス型の宣言](../dotnet/declaration-of-a-managed-class-type.md)  
 マネージ型の `class`、`struct`、または `interface` の宣言の方法について説明します。  
  
 [CLR 参照クラスのオブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 追跡ハンドルによる参照クラス型オブジェクトの宣言の方法について説明します。  
  
 [CLR 配列の宣言](../dotnet/declaration-of-a-clr-array.md)  
 配列の宣言と初期化の方法について説明します。  
  
 [コンストラクターの初期化処理の順序における変更](../Topic/Changes%20in%20Constructor%20Initialization%20Order.md)  
 クラス コンストラクターの初期化処理の順序が変更されました。主な変更点について説明します。  
  
 [デストラクターのセマンティクスの変更](../dotnet/changes-in-destructor-semantics.md)  
 非確定的な終了処理、`Finalize` と `Dispose`、参照オブジェクトの影響、明示的 `Finalize` の使用について説明します。  
  
 **メモ :** デリゲートについては後の「[デリゲートとイベント](../dotnet/delegates-and-events.md)」で説明しますが、これは全般的なトピックである「[クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)」で取り上げるクラス内のイベント メンバーと合わせて説明するためです。  
  
## 参照  
 [C\+\+\/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)