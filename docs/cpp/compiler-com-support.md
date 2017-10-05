---
title: "コンパイラ COM サポート |Microsoft ドキュメント"
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
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d81c54f7af604024da852999ca78fa5ee55079ef
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-support"></a>コンパイラの COM サポート
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 Visual C++ コンパイラはコンポーネント オブジェクト モデル (COM) タイプ ライブラリを直接読み取り、コンパイルに含めることのできる C++ ソース コードにコンテンツを変換します。 言語拡張機能はクライアント側の COM プログラミングを簡単にします。  
  
 使用して、 [#import プリプロセッサ ディレクティブ](../preprocessor/hash-import-directive-cpp.md)コンパイラがタイプ ライブラリを読み取ることができます、およびクラスのインターフェイスとして COM を記述する C++ ヘッダー ファイルに変換します。 一連の `#import` 属性は、結果の種類のライブラリのヘッダー ファイルのコンテンツのユーザー コントロールで使用できます。  
  
 使用することができます、 [_ _declspec](../cpp/declspec.md)拡張属性[uuid](../cpp/uuid-cpp.md)を COM オブジェクトへのグローバル一意識別子 (GUID) を割り当てます。 キーワード[_ _uuidof](../cpp/uuidof-operator.md) COM オブジェクトに関連付けられている GUID を抽出するために使用できます。 別`__declspec`属性、[プロパティ](../cpp/property-cpp.md)を指定するために使用する、**取得**と**設定**COM オブジェクトのデータ メンバーのメソッドです。  
  
 サポートする一連の COM サポート グローバル関数とクラスが提供される、**バリアント**と`BSTR`型、スマート ポインターを実装およびによってスローされたエラー オブジェクトをカプセル化`_com_raise_error`:  
  
-   [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)  
  
-   [_bstr_t](../cpp/bstr-t-class.md)  
  
-   [_com_error](../cpp/com-error-class.md)  
  
-   [_com_ptr_t](../cpp/com-ptr-t-class.md)  
  
-   [_variant_t](../cpp/variant-t-class.md)  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)   
 [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)
