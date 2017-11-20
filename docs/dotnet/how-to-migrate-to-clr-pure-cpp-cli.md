---
title: "方法: clr への移行: 純粋な (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], migrating to /clr:pure
- migration [C++], pure MSIL
- pure MSIL [C++], porting to
ms.assetid: 5ffb1184-2095-4ade-84aa-4fa6324bc764
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ebff4ae1ac304ee0af073de49f4ee988922247d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-migrate-to-clrpure-ccli"></a>方法: /clr:pure に移行する (C++/CLI)
純粋 MSIL を使用してに移行するときに発生する可能性がある問題について説明**/clr: 純粋な**(を参照してください[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)詳細については)。 このトピックでは、移行中のコードが現在を使用して混在のアセンブリとしてコンパイルを前提としています、 **/clr**オプション、純粋 MSIL にアンマネージ コードからの移行パスは、直接的ではありません。 アンマネージ コードは、次を参照してください。[する方法:/clr:pure に移行](../dotnet/how-to-migrate-to-clr.md)純粋 MSIL に移行する前にします。  
  
## <a name="basic-changes"></a>基本的な変更  
 純粋 MSIL は、MSIL では表現できない関数が含まれるコードはコンパイルを防ぐために、MSIL 命令で構成されます。 呼び出し規約を使用する以外の値として定義されている関数を含む[_ _clrcall](../cpp/clrcall.md)です。 (非 _ _clrcall 関数できます純粋 MSIL コンポーネントで呼び出されますが定義されていません。)  
  
 ランタイム エラーしないようにするには、C4412 警告を有効にする必要があります。 C4412 を追加することで有効にする`#pragma warning (default : 4412)`でコンパイルする各コンパイル単位に**/clr: 純粋な**IJW との間の C++ の型をパスして (**/clr)**またはネイティブ コード。 参照してください[コンパイラの警告 (レベル 2) C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md)詳細についてはします。  
  
## <a name="architectural-considerations"></a>アーキテクチャの考慮事項  
 一覧にある純粋 MSIL アセンブリの制限の一部が[純粋なコードと検証可能なコード (C + + CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)アプリケーションの設計と移行戦略の高度な影響があります。 特に、混在アセンブリとは異なり純粋 MSIL アセンブリしないご利用いただけますアンマネージ モジュールとの完全な互換性。  
  
 純粋 MSIL アセンブリでは、アンマネージ関数を呼び出すことができますが、アンマネージ関数から呼び出すことはできません。 その結果、純粋な MSIL は、アンマネージ関数によって使用されるサーバー コードよりもアンマネージ関数を使用するクライアント コード向上候補です。 純粋 MSIL アセンブリに含まれる機能をアンマネージ関数で使用する場合は、混在アセンブリは、インターフェイス レイヤーとして使用する必要があります。  
  
 ATL または MFC を使用するアプリケーションは、これらのライブラリは、このリリースでサポートされていないので、純粋 MSIL への移行の候補ではありません。 同様に、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]ではコンパイルされないヘッダー ファイルを含む**/clr: 純粋な**します。  
  
 純粋 MSIL アセンブリでは、アンマネージ関数を呼び出すことができます、この機能は、単純な C スタイルの関数に限られます。 複雑なアンマネージ Api の使用は、アンマネージ COM インターフェイスまたは純粋 MSIL とアンマネージ コンポーネント間のインターフェイスとして機能する混在アセンブリの形式で公開する機能を必要とする可能性があります。 純粋なアセンブリがコールバックとして使用するためのネイティブ呼び出し可能な関数を提供することではない例については、コールバック関数を受け取るアンマネージ関数を使用する唯一の方法は、混在アセンブリを使用します。  
  
## <a name="application-domains-and-calling-conventions"></a>アプリケーション ドメインと呼び出し規約  
 できますがアセンブリを純粋 msil には、管理されていない機能を関数を使用して、静的なデータの処理は異なります。 純粋なアセンブリは、関数が実装されて、 [_ _clrcall](../cpp/clrcall.md)ストアドごとにアプリケーション ドメインは、呼び出し規約、および静的データです。 これは、アンマネージおよび混在アセンブリの既定値とは異なります、 [_ _cdecl](../cpp/cdecl.md)関数の呼び出し規約と、プロセスごとに静的なデータを格納します。  
  
 純粋 MSIL (および/clr:safe と共にコンパイルされた検証可能なコード) のコンテキスト内でこれらの既定値は、 [_ _clrcall](../cpp/clrcall.md) CLR の既定の呼び出し規約は、アプリケーション ドメインが静的のネイティブのスコープと.NET アプリケーションのグローバル データ。 ただし、アンマネージまたは混合のコンポーネントとやり取りして、関数とグローバル データの処理の違いが原因の問題。  
  
 たとえば、純粋 MSIL コンポーネントは、アンマネージまたは混在 DLL 内で関数を呼び出すには、純粋なアセンブリをコンパイルする、DLL のヘッダー ファイルを使用するされます。 ただし、ヘッダー内の各関数の呼び出し規則が明示的に示されている場合を除き、これらはすべてと見なされます[_ _clrcall](../cpp/clrcall.md)です。 これは後で実行時の障害とさせるで実装される可能性がこれらの関数、 [_ _cdecl](../cpp/cdecl.md)規則。 アンマネージ ヘッダー ファイル内の関数を明示的としてマークできる[_ _cdecl](../cpp/cdecl.md)、または下にある DLL ソース コード全体を再コンパイルする必要があります**/clr: 純粋な**します。  
  
 同様に、関数ポインターと見なされます をポイント[_ _clrcall](../cpp/clrcall.md)で機能**/clr: 純粋な**コンパイルします。 これらもする必要があります明示的にで注釈を付ける正しい呼び出し規約です。  
  
 詳細については、次を参照してください。[アプリケーション ドメインと Visual c](../dotnet/application-domains-and-visual-cpp.md)です。  
  
## <a name="linking-limitations"></a>リンクに関する制限事項  
 Visual C リンカーはしません混合、純粋なの OBJ ファイルにリンクするように、記憶域のスコープと呼び出し規約が異なる。  
  
## <a name="see-also"></a>関連項目  
 [純粋なコードと検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)