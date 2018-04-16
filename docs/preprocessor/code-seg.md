---
title: "code_seg |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
dev_langs:
- C++
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57511efccff22a1f1d6e7dcd957d75066b072c55
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="codeseg"></a>code_seg
関数が格納される .obj ファイル内のテキスト セグメントを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>コメント  
 `code_seg` プラグマ ディレクティブは、インスタンス化されたテンプレート用に生成されたオブジェクト コードや、コンパイラによって暗黙的に生成されたコード (特殊なメンバー関数など) の格納場所を制御するものではありません。 使用することをお勧め、 [__declspec(code_seg(...)](../cpp/code-seg-declspec.md)属性代わりに使用することにより、すべてのオブジェクト コードの配置を制御します。 コンパイラによって生成されたコードの格納場所も制御できるためです。  
  
 A*セグメント*.obj ファイルは名前付きのユニットとしてメモリに読み込まれるデータのブロックです。 A*テキスト セグメント*セグメントでは、実行可能コードが含まれています。 この記事で、条項*セグメント*と*セクション*は同義です。  
  
 `code_seg` プラグマ ディレクティブは、翻訳単位の後続のすべてのオブジェクト コードを `segment-name` というテキスト セグメントに格納するように、コンパイラに指示します。 既定では、.obj ファイル内の関数に使用されるテキスト セグメントには .text という名前が付けられます。  
  
 `code_seg` プラグマ ディレクティブは、パラメーターが指定されない場合、後続のオブジェクト コードのテキスト セグメント名を .text にリセットします。  
  
 **プッシュ**(省略可能)  
 レコードを内部コンパイラ スタックに格納します。 A**プッシュ**持つことができます、`identifier`と`segment-name`です。  
  
 **pop** (省略可能)  
 内部コンパイラ スタックの最上部からレコードを削除します。  
  
 `identifier` (省略可能)  
 使用すると**プッシュ**、内部コンパイラ スタックのレコードに名前が割り当てられます。 使用すると**pop**、レコードまで内部スタックからポップ`identifier`が削除された場合`identifier`がない内部スタックで、何もポップします。  
  
 `identifier` により、複数のレコードが 1 つだけでポップできます**pop**コマンド。  
  
 "`segment-name`" (省略可能)  
 引数の名前。 使用すると**pop**、スタックがポップされますと`segment-name`アクティブなテキスト セグメント名になります。  
  
 "`segment-class`" (省略可能)  
 無視されますが、C++ 2.0 より前のバージョンとの互換性を保つために残されています。  
  
 使用することができます、 [DUMPBIN です。EXE](../build/reference/dumpbin-command-line.md) .obj ファイルを表示するアプリケーション。 サポートされている各ターゲット アーキテクチャの DUMPBIN のバージョンは [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] に付属しています。  
  
## <a name="example"></a>例  
 この例では、`code_seg` プラグマ ディレクティブを使用して、オブジェクト コードの格納場所を制御する方法を示しています。  
  
```  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
 セクションを作成するのには使用できません名の一覧は、次を参照してください。 [/section](../build/reference/section-specify-section-attributes.md)です。  
  
 初期化されたデータのセクションを指定することもできます ([data_seg](../preprocessor/data-seg.md))、初期化されていないデータ ([bss_seg](../preprocessor/bss-seg.md))、および const 変数 ([const_seg](../preprocessor/const-seg.md))。  
  
## <a name="see-also"></a>参照  
 [code_seg (__declspec)](../cpp/code-seg-declspec.md)   
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)