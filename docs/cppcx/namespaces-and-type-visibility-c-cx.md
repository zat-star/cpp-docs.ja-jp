---
title: "名前空間と型の参照範囲 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
caps.latest.revision: 13
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 13
---
# 名前空間と型の参照範囲 (C++/CX)
名前空間は、関連する機能を持つ型をグループ化し、ライブラリ内での名前の衝突を回避するための、標準の C\+\+ 構造体です。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]型システムでは、独自コード内にあるものも含め、すべてのパブリック [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]型を名前空間スコープの名前空間で宣言する必要があります。 パブリック型をグローバル スコープで宣言したり、別のクラスの中に入れ子にしたりすると、コンパイル時エラーが発生します。  
  
 .winmd ファイルには、ルート名前空間と同じ名前が必要です。 たとえば、A.B.C.MyClass という名前のクラスは、A.winmd または A.B.winmd または A.B.C.winmd という名前のメタデータ ファイルで定義されている場合のみインスタンス化できます。 実行可能ファイルの名前が .winmd ファイル名と一致する必要はありません。  
  
## 型の可視性  
 名前空間では、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型は標準 C\+\+ 型とは異なり、プライベートまたはパブリックのいずれかのアクセシビリティを持ちます。 既定では、アクセシビリティはプライベートです。 メタデータから参照できるのはパブリック型だけです。したがって、C\+\+ 以外の言語で記述されている可能性もあるコンポーネントとアプリから利用できるのもパブリック型だけです。 一般に、参照可能な型の規則は、参照できない型の規則よりも制限的です。これは、.NET 言語および JavaScript でサポートされていない C\+\+ 固有の概念を参照可能な型が公開できないためです。  
  
> [!NOTE]
>  .NET 言語および JavaScript がメタデータを利用できるのは、実行時のみです。 C \+\+ アプリまたはコンポーネントが、他の C \+\+ アプリまたはコンポーネント \(これには、すべて C\+\+ で記述された Windows コンポーネントも含まれます\) と通信中のときは、メタデータの実行時利用は不要です。  
  
## メンバーのアクセシビリティおよび可視性  
 プライベートの ref クラス、インターフェイス、またはデリゲートでは、パブリック アクセシビリティがあっても、メンバーはメタデータには出力されません。 パブリック ref クラスでは、ソース コードでのアクセシビリティとは無関係に、メタデータのメンバーの可視性を制御できます。 標準 C\+\+ と同様に、最小特権の基本原則を適用します。絶対にそうする必要がある場合を除き、メタデータでメンバーを可視にしないでください。  
  
 次のアクセス修飾子を使用して、メタデータの可視性およびソース コード アクセシビリティを制御します。  
  
||||  
|-|-|-|  
|修飾子|説明|メタデータに出力されるか。|  
|private|既定のアクセシビリティ。 標準 C\+\+ の場合と同じ意味です。|いいえ|  
|protected|標準 C\+\+ の場合と同じ意味であり、アプリまたはコンポーネント内およびメタデータ内では両方。|はい|  
|public|標準 C\+\+ の場合と同じ意味です。|はい|  
|`public protected` または `protected public`|メタデータでは保護されたアクセシビリティ、アプリまたはコンポーネント内ではパブリック。|はい|  
|`protected private` または `private protected`|メタデータでは非可視。アプリまたはコンポーネント内では保護されたアクセシビリティ。||  
|`internal` または `private public`|メンバーは、アプリまたはコンポーネント内ではパブリックですが、メタデータでは非可視です。|いいえ|  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 名前空間  
 Windows API は、Windows::\* 名前空間で宣言された型で構成されます。 これらの名前空間は Windows 用に予約されており、それらの名前空間に型を追加できません。**オブジェクト ブラウザー**では、windows.winmd ファイル内でこれらの名前空間を表示できます。 これらの名前空間に関するドキュメントについては、「[Windows API](http://msdn.microsoft.com/library/windows/apps/br211377)」を参照してください。  
  
## [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 名前空間  
 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) は、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型システムのプロジェクションの一部として、これらの名前空間の特定の型を定義します。  
  
|||  
|-|-|  
|**名前空間**|**説明**|  
|default|組み込みの数値型と char16 型を格納します。 これらの型はすべての名前空間のスコープ内にあり、`using` ステートメントは必要ではありません。|  
|プラットフォーム|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]、`Array<T>`、`String`、および `Guid` など、主に `Boolean` 型に対応するパブリック型を格納します。 また、`Platform::Agile<T>` および `Platform::Box<T>` などの、特殊なヘルパー型も含まれます。|  
|Platform::Collections|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]、`IVector` などの `IMap` コレクション インターフェイスを実装する、具体的なコレクション クラスを格納します。 これらの型は、platform.winmd ではなく、ヘッダー ファイル、collection.h で定義されます。|  
|Platform::Details|コンパイラによって使用され、パブリックでの使用を意図されていない型を格納します。|  
  
## 参照  
 [型システム \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)