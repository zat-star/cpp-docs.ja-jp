---
title: "コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.component
- component_CPP
dev_langs:
- C++
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3edb2f68b479eeadca777e0707dd96e148d13fe8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="component"></a>コンポーネント
ブラウザー情報または依存関係情報の収集をソース ファイル内から制御します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## <a name="remarks"></a>コメント  
  
## <a name="browser"></a>ブラウザー  
 情報収集のオン/オフを切り替えます。また特定の名前を指定して情報収集の際に無視できます。  
  
 on または off を使用して、このプラグマ以降のブラウザー情報の収集を制御します。 例:  
  
```  
#pragma component(browser, off)  
```  
  
 上のプラグマは、コンパイラによるブラウザー情報の収集を停止します。  
  
> [!NOTE]
>  このプラグマを使用してブラウザー情報の収集を有効にする[ブラウザー情報を最初に有効にする](../build/reference/building-browse-information-files-overview.md)です。  
  
 **参照**有無にかかわらず、オプションを使用できます、*名前*引数。 使用して**参照**せず*名前*オンまたはオフの収集の (ただし、収集するその他の参照情報が続行されます)。 例:  
  
```  
#pragma component(browser, off, references)  
```  
  
 このプラグマは、コンパイラによる参照情報の収集を停止します。  
  
 使用して**参照**で*名前*と**オフ**への参照を防止*名前*ブラウズ情報ウィンドウに表示されないようにします。 この構文を使用して必要のない名前と型を無視することで、ブラウザー情報ファイルのサイズを縮小できます。 例:  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 参照は無視されます**DWORD**その時点からです。 参照の収集を有効にする`DWORD`上のバックアップを使用して**で**:  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 参照の収集を再開する唯一の方法は、この*名前*; いずれかに明示的に有効にする必要があります*名前*オフにしていること。  
  
 プリプロセッサが展開するを防ぐため*名前*(展開など**NULL**に**0**)、引用符で囲みます。  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## <a name="minimal-rebuild"></a>最小リビルド  
 Visual C++ の最小リビルド機能は、コンパイラが C++ のクラスの依存関係情報を作成して保存する必要があるため、ディスク容量が使用されます。 使用できるディスク容量を節約する`#pragma component( minrebuild, off )`不変のヘッダー ファイルで、インスタンスの依存関係情報を収集するときにする必要はありません。 挿入`#pragma component(minrebuild, on)`終了に戻すに依存関係コレクションを有効にする変更のないクラスです。  
  
## <a name="reduce-type-information"></a>型情報の削減  
 **Mintypeinfo**オプションが指定されている領域のデバッグ情報を削減します。 この情報は量が多く、.pdb ファイルと .obj ファイルに影響を与えます。 mintypeinfo 領域では、クラスと構造をデバッグできません。 mintypeinfo オプションを使用すると、次の警告を回避するのに役立ちます。  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 詳細については、次を参照してください。、[最小リビルドを有効にする](../build/reference/gm-enable-minimal-rebuild.md)(/Gm) コンパイラ オプション。  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)