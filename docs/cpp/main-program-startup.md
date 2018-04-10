---
title: 'main: プログラムの起動 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- vc.main.startup
- _tmain
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fbb3d19101358012df795000907a0b3e8139601
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="main-program-startup"></a>main: プログラムの起動
という名前の特殊な関数`main`すべての C および C++ プログラムの実行の開始ポイントです。 [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] プログラミング モデルに準拠するコードを書く場合は、`wmain` のワイド文字バージョンである `main` を使用できます。  
  
 `main` 関数は、コンパイラによってあらかじめ定義されていません。 これは、プログラム テキストに記述する必要があります。  
  
 `main` の宣言構文は次のとおりです。  
  
```  
int main();  
```  
  
 または、必要に応じて次のように記述します。  
  
```  
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Microsoft 固有の仕様 →  
 `wmain` の宣言構文は次のとおりです。  
  
```  
int wmain( );  
```  
  
 または、必要に応じて次のように記述します。  
  
```  
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 TCHAR.h で定義されている `_tmain` を使用することもできます。 _UNICODE が定義されていない場合、`_tmain` は `main` に解決されます。 定義されている場合、`_tmain` は `wmain` に解決されます。  
  
 または、`main` および `wmain` 関数を `void` (戻り値なし) を返すように宣言できます。 宣言する場合`main`または`wmain`を返すよう`void`を使用して、親プロセスやオペレーティング システムに終了コードを返すことはできません、[返す](../cpp/return-statement-in-program-termination-cpp.md)ステートメントです。 返される、ときに終了コード`main`または`wmain`として宣言されている`void`、使用する必要があります、[終了](../cpp/exit-function.md)関数。  
  
**Microsoft 固有の仕様はここまで**  
 `argc` と `argv` の型は、言語によって定義されています。 名前 `argc`、`argv`、および`envp` は従来のものですが、コンパイラにとって必須ではありません。 例および詳細については、次を参照してください。[引数定義](../cpp/argument-definitions.md)です。  
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)   
 [Main に代わる wmain の使用](../cpp/using-wmain-instead-of-main.md)   
 [main 関数に関する制約](../cpp/main-function-restrictions.md)