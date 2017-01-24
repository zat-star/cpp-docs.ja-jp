---
title: "C++ クラスでの dllimport と dllexport の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], 宣言"
  - "クラス [C++], エクスポート可能と継承"
  - "宣言 [C++], class"
  - "宣言 (クラスの)"
  - "dllexport 属性 [C++]"
  - "dllexport 属性 [C++], クラス"
  - "dllimport 属性 [C++], クラス"
  - "エクスポート可能クラス [C++]"
  - "エクスポート (クラスを)"
  - "継承 [C++], エクスポート可能クラス"
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ クラスでの dllimport と dllexport の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 **dllimport** 属性または `dllexport` 属性を使用して C\+\+ クラスを宣言できます。  これらの形式は、クラス全体がインポートまたはエクスポートされることを暗黙的に指定します。  この方法でエクスポートされたクラスは、エクスポート可能なクラスと呼ばれます。  
  
 次の例では、エクスポート可能なクラスを定義しています。  そのメンバー関数と静的データはすべてエクスポートされます。  
  
```  
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 エクスポート可能なクラスのメンバーに明示的に **dllimport** 属性と `dllexport` 属性を使用することは禁止されています。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a> dllexport クラス  
 `dllexport` クラスを宣言すると、そのメンバー関数と静的データ メンバーがすべてエクスポートされます。  このようなすべてのメンバーは同じプログラム内で定義する必要があります。  定義しない場合は、リンカー エラーが生成されます。  この規則の例外は純粋仮想関数です。純粋仮想関数にはこのような明示的な定義は不要です。  ただし、抽象クラスのデストラクターは基底クラスのデストラクターによって常に呼び出されるため、純粋仮想デストラクターには常に明示的な定義が必要です。  これらの規則はエクスポート不可クラスに対しても同じであることに注意してください。  
  
 クラス型のデータまたはクラスを返す関数をエクスポートする場合、必ずそのクラスもエクスポートしてください。  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a> dllimport クラス  
 **dllimport** クラスを宣言すると、そのメンバー関数と静的データ メンバーがすべてインポートされます。  非クラス型に対する **dllimport** と `dllexport` の動作とは異なり、静的データ メンバーは **dllimport** のクラスが定義されている同じプログラム内に定義することはできません。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a> 継承とエクスポート可能なクラス  
 エクスポート可能なクラスのすべての基底クラスはエクスポート可能である必要があります。  そうでない場合、コンパイラ警告が生成されます。  また、クラスでもあるアクセス可能なメンバーはすべてエクスポート可能である必要があります。  この規則は、`dllexport` クラスが **dllimport** クラスから継承され、**dllimport** クラスが `dllexport` クラスから継承されることを許可します \(後者はお勧めしません\)。  一般的に、DLL のクライアントからアクセス可能な \(C\+\+ のアクセス規則に従って\) すべてのものは、エクスポート可能なインターフェイスの一部である必要があります。  たとえば、インライン関数で参照されるプライベート データ メンバーなどです。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a> 選択的なメンバーのインポート\/エクスポート  
 クラス内のメンバー関数と静的データには暗黙的に外部リンケージがあるため、クラス全体をエクスポートしない場合は、そのメンバー関数とデータを **dllimport** または `dllexport` 属性で宣言できます。  クラス全体をインポートまたはエクスポートする場合、そのメンバー関数とデータを **dllimport** または `dllexport` と明示的に宣言することはできません。  クラス定義内の静的データ メンバーを `dllexport` として宣言する場合は、同じプログラム内で定義する必要があります \(非クラス外部リンケージの場合と同様\)。  
  
 同じように、**dllimport** 属性または `dllexport` 属性を使用してメンバー関数を宣言できます。  この場合、同じプログラム内に `dllexport` 定義が必要です。  
  
 選択的なメンバーのインポート\/エクスポートには、次のいくつかの重要な点に注意してください。  
  
-   選択的なメンバーのインポート\/エクスポートは、より制限が厳しい、エクスポートされたクラス インターフェイスのバージョン \(つまり、言語で許容されるよりも少ないパブリック機能およびプライベート機能を公開する DLL を設計できるバージョン\) を提供する場合に最適です。  また、エクスポート可能なインターフェイスを最適化するためにも便利です。クライアントがプライベート データにアクセスできない場合は、もちろん、クラス全体をエクスポートする必要はありません。  
  
-   クラス内の 1 つの仮想関数をエクスポートする場合、それらの関数のすべてをエクスポートするか、少なくともクライアントが直接使用できるバージョンを提供する必要があります。  
  
-   仮想関数で使用する選択的なメンバーのインポート\/エクスポートを行うクラスがある場合、それらの関数はエクスポート可能なインターフェイスまたは定義済みインライン内 \(クライアントから参照可能\) にある必要があります。  
  
-   メンバーを `dllexport` として定義したが、クラス定義には含めなかった場合、コンパイラ エラーが生成されます。  クラスのヘッダーでメンバーを定義する必要があります。  
  
-   クラス メンバーを **dllimport** または `dllexport` として定義することはできますが、クラス定義内に指定しているインターフェイスをオーバーライドすることはできません。  
  
-   メンバー関数を宣言したクラス定義の本体以外でその関数を定義する場合、この関数を `dllexport` または **dllimport** として定義すると \(この定義がクラス宣言内の定義と異なると\)、警告が生成されます。  
  
### END Microsoft 固有の仕様  
  
## 参照  
 [dllexport、dllimport](../cpp/dllexport-dllimport.md)