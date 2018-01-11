---
title: "いったん |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.once
- once_CPP
dev_langs: C++
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c04d411a6b0075d2fa08d846ad3b8a1bbb020c17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="once"></a>once
ソース コード ファイルをコンパイルする際、コンパイラによってファイルが 1 回だけ取り込まれる (開かれる) ようにします。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma once  
  
```  
  
## <a name="remarks"></a>コメント  
 `#pragma once` を使用すると、翻訳単位でファイルの最初の #include の実行後にコンパイラで同じファイルを開いて読み込むことがないので、ビルド時間を短縮できます。 これを呼びます*複数インクルードの最適化*です。 同様の効果がある、 *#include guard の include*表現形式は、プリプロセッサ マクロの定義を使用して、ファイルの内容が複数回インクルードを防ぐためです。 違反を防ぐためには、*単一定義規則*— すべてのテンプレート、型、関数、およびオブジェクトがある 2 つ以上の定義、コード内の要件です。  
  
 例:  
  
```  
// header.h  
#pragma once  
// Code placed here is included only once per translation unit  
  
```  
  
 新しいコードには `#pragma once` ディレクティブを使用することをお勧めします。これを使えば、プリプロセッサ シンボルによるグローバル名前空間のポリューションが発生しないためです。 またこのディレクティブは、必要な入力量や無駄も少なく、シンボルの競合の原因にもなりません。シンボルの競合とは、異なるヘッダー ファイルで同じプリプロセッサ シンボルがガード値として使用されたときに発生するエラーです。 これは C++ の標準の一部ではありませんが、いくつかの一般的なコンパイラにより移植可能な方法で実装されます。  
  
 同じファイルで #include guard 表現形式と `#pragma once` の両方を使用する利点はありません。 コメントではないコードまたはプリプロセッサ ディレクティブが標準的な表現形式の前後にくる場合、`#pragma once` ディレティブと同様の方法で、コンパイラにより #include guard 表現形式が認識され、複数インクルードの最適化が実装されます。  
  
```  
// header.h  
// Demonstration of the #include guard idiom.  
// Note that the defined symbol can be arbitrary.  
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_  
#define HEADER_H_  
// Code placed here is included only once per translation unit  
#endif // HEADER_H_  
  
```  
  
 既存のコードとの一貫性を維持するために、`#pragma once` ディレクティブを実装していないコンパイラにコードを移植できるようにする必要がある場合や、複数のインクルードの最適化が不可能である場合は、#include guard 表現形式をお勧めします。 これは、ファイル システムの別名または別名が設定されたインクルード パスにより、コンパイラが正規のパスを基準に同じインクルード ファイルを識別できなくなるような複雑なプロジェクトで発生する場合があります。  
  
 プリプロセッサ シンボルを使用してその効果を制御する、複数回のインクルードが発生するように設計されているヘッダー ファイルに、`#pragma once` または #include guard の表現形式を使用しないようにします。 この設計の例は、次を参照してください。、 \<assert.h > ヘッダー ファイルです。 また、インクルード ファイルに複数のパスを作成すると、#include guard と `#pragma once` の両方で複数インクルードの最適化が損なわれるため、インクルード パスを慎重に管理し、それを回避してください。  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)