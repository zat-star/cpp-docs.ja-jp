---
title: "セキュリティ保護されたテンプレート オーバーロード | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES
- _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT
dev_langs:
- C++
helpviewer_keywords:
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES
- _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT
- secure template overloads
ms.assetid: 562741d0-39c0-485e-8529-73d740f29f8f
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1519fde9f60f9cb9b45db4a4921f2bec5185e549
ms.lasthandoff: 02/24/2017

---
# <a name="secure-template-overloads"></a>セキュリティ保護されたテンプレート オーバーロード
多くの CRT 関数が、新しいセキュリティが強化されたバージョンに置き換えられています (たとえば、`strcpy` はセキュリティが強化された `strcpy_s` に置き換わっています)。 CRT では、セキュリティが強化されたバリアントに簡単に遷移するためのテンプレート オーバーロードが用意されています。  
  
 たとえば、`strcpy` が使用されなくなっているため、次のコードでは警告が発生します。  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // warning: deprecated`  
  
 この警告は無視してかまいません。 シンボル `_CRT_SECURE_NO_WARNINGS` を定義して警告を抑制するか、コードを更新して `strcpy_s` を使用します。  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, 10, "test"); // security-enhanced _s function`  
  
 テンプレート オーバーロードを使用することもできます。 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` を 1 に定義すると、セキュリティが強化されたバリアントを自動的に呼び出す、標準 CRT 関数のテンプレート オーバーロードが有効になります。 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` が 1 の場合、コードを変更する必要はありません。 内部では、`strcpy` の呼び出しが `strcpy_s` の呼び出しに変換され、サイズ引数が自動的に指定されます。  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` は、`strncpy` などのカウントを確認する関数には影響しません。 カウント関数に対するテンプレート オーバーロードを有効にするには、`_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` を 1 に定義します。 ただし、定義する前に、コードがバッファー サイズ (よくある間違い) ではなく、文字数を渡しているかどうかを確認しておく必要があります。 また、セキュリティで保護されたバリアントを呼び出す場合、関数の呼び出し後、バッファーの最後に明示的に null 終端文字を書き込むコードも必要です。 切り捨て動作が必要な場合は、「[_TRUNCATE](../c-runtime-library/truncate.md)」を参照してください。  
  
> [!NOTE]
>  マクロ `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` では、`_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` も 1 と定義されている必要があります。 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` が 1 と定義されていて、`_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` が 0 と定義されている場合、アプリケーションはテンプレート オーバーロードを実行しません。  
  
 `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` を 1 に定義すると、セキュリティで保護されたバリアント (名前の最後に "_s" が付いています) のテンプレート オーバーロードが有効になります。 この場合、`_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` が 1 であれば、元のコードに対して小さな変更が 1 つ必要になります。  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 関数名のみ変更する必要があります ("_s" を追加します)。サイズ引数については、テンプレート オーバーロードが処理します。  
  
 既定では、`_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` および `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` は 0 (無効) に定義され、`_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` は 1 (有効) に定義されています。  
  
 これらのテンプレート オーバーロードは、静的な配列に対してのみ作用します。 動的に割り当てられるバッファーの場合、ソース コードにさらに変更が必要になります。 上記の例をもう一度使用します。  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy(szBuf, "test"); // still deprecated; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
 および  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy_s(szBuf, "test"); // doesn't compile; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
## <a name="see-also"></a>関連項目  
 [CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)   
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)
