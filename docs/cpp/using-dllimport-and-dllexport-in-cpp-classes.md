---
title: "C++ クラスでの dllimport と dllexport の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exporting classes [C++]
- declarations [C++], class
- exportable classes [C++]
- classes [C++], declaring
- classes [C++], exportable and inheritance
- inheritance [C++], exportable classes [C++]
- dllimport attribute [C++], classes
- declaring classes [C++]
- dllexport attribute [C++]
- dllexport attribute [C++], classes [C++]
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6085672be99f6ddeb6d5b124eaf62f34e67e45f9
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ クラスでの dllimport と dllexport の使用
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 C++ のクラスを宣言することができます、 **dllimport**または`dllexport`属性。 これらの形式は、クラス全体がインポートまたはエクスポートされることを暗黙的に指定します。 この方法でエクスポートされたクラスは、エクスポート可能なクラスと呼ばれます。  
  
 次の例では、エクスポート可能なクラスを定義しています。 そのメンバー関数と静的データはすべてエクスポートされます。  
  
```  
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 その明示的な使用に注意してください、 **dllimport**と`dllexport`エクスポート可能なクラスのメンバーの属性が禁止されています。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a>dllexport クラス  
 `dllexport` クラスを宣言すると、そのメンバー関数と静的データ メンバーがすべてエクスポートされます。 このようなすべてのメンバーは同じプログラム内で定義する必要があります。 定義しない場合は、リンカー エラーが生成されます。 この規則の例外は純粋仮想関数です。純粋仮想関数にはこのような明示的な定義は不要です。 ただし、抽象クラスのデストラクターは基底クラスのデストラクターによって常に呼び出されるため、純粋仮想デストラクターには常に明示的な定義が必要です。 これらの規則はエクスポート不可クラスに対しても同じであることに注意してください。  
  
 クラス型のデータまたはクラスを返す関数をエクスポートする場合、必ずそのクラスもエクスポートしてください。  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a>dllimport クラス  
 クラスを宣言すると**dllimport**、そのすべてのメンバー関数と静的データ メンバーがインポートされます。 動作とは異なり**dllimport**と`dllexport`、クラス型に対する静的データ メンバーを同じプログラム内での定義を指定できません、 **dllimport**クラスが定義されています。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a>継承とエクスポート可能クラス  
 エクスポート可能なクラスのすべての基底クラスはエクスポート可能である必要があります。 そうでない場合、コンパイラ警告が生成されます。 また、クラスでもあるアクセス可能なメンバーはすべてエクスポート可能である必要があります。 この規則により、`dllexport`から継承するクラス、 **dllimport**クラス、および**dllimport**から継承するクラス、`dllexport`クラス (ただし、後者は推奨されません)。 一般的に、DLL のクライアントからアクセス可能な (C++ のアクセス規則に従って) すべてのものは、エクスポート可能なインターフェイスの一部である必要があります。 たとえば、インライン関数で参照されるプライベート データ メンバーなどです。  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a>選択的なメンバーのインポート/エクスポート  
 メンバー関数とクラス内で静的なデータが外部リンケージが暗黙的に、それらを宣言できます、 **dllimport**または`dllexport`属性がクラス全体をエクスポートしない限り、します。 クラス全体がインポートまたはエクスポートするメンバー関数とデータとしての明示的な宣言**dllimport**または`dllexport`は禁止されています。 クラス定義内の静的データ メンバーを `dllexport` として宣言する場合は、同じプログラム内で定義する必要があります (非クラス外部リンケージの場合と同様)。  
  
 同様に、できるメンバーを宣言する関数、 **dllimport**または`dllexport`属性。 この場合、同じプログラム内に `dllexport` 定義が必要です。  
  
 選択的なメンバーのインポート/エクスポートには、次のいくつかの重要な点に注意してください。  
  
-   選択的なメンバーのインポート/エクスポートは、より制限が厳しい、エクスポートされたクラス インターフェイスのバージョン (つまり、言語で許容されるよりも少ないパブリック機能およびプライベート機能を公開する DLL を設計できるバージョン) を提供する場合に最適です。 また、エクスポート可能なインターフェイスを最適化するためにも便利です。クライアントがプライベート データにアクセスできない場合は、もちろん、クラス全体をエクスポートする必要はありません。  
  
-   クラス内の 1 つの仮想関数をエクスポートする場合、それらの関数のすべてをエクスポートするか、少なくともクライアントが直接使用できるバージョンを提供する必要があります。  
  
-   仮想関数で使用する選択的なメンバーのインポート/エクスポートを行うクラスがある場合、それらの関数はエクスポート可能なインターフェイスまたは定義済みインライン内 (クライアントから参照可能) にある必要があります。  
  
-   メンバーを `dllexport` として定義したが、クラス定義には含めなかった場合、コンパイラ エラーが生成されます。 クラスのヘッダーでメンバーを定義する必要があります。  
  
-   クラス メンバーの定義**dllimport**または`dllexport`は許可されている場合、クラス定義で指定されたインターフェイスをオーバーライドすることはできません。  
  
-   宣言をクラス定義の本体以外で、メンバー関数を定義する場合として、関数が定義されている場合に、警告が生成`dllexport`または**dllimport** (この定義とは異なる場合指定されたクラス宣言内)。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [dllexport、dllimport](../cpp/dllexport-dllimport.md)
