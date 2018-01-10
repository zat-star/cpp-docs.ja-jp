---
title: "-Zc: wchar_t (wchar_t をネイティブ型) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
dev_langs: C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3375e39120fdc8f2b0d8d5502aa6def997511ff5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t をネイティブ型として認識)
`wchar_t` を、C++ 標準に従って組み込み型として解析します。 既定では、 **/Zc:wchar_t**にします。  
  
## <a name="syntax"></a>構文  
  
```  
/Zc:wchar_t[-]  
```  
  
## <a name="remarks"></a>コメント  
 場合**/Zc:wchar_t**が有効になって`wchar_t`Microsoft 固有のネイティブ型にマップ`__wchar_t`です。 場合**/Zc:wchar_t-** (マイナス記号) を指定すると、`wchar_t`にマップする`typedef`の`unsigned short`します。 (Visual C++ 6.0 以前では、`wchar_t` は、組み込み型として実装されていたのではなく、`typedef` の `unsigned short` として wchar.h で宣言されていました)。お勧めしません**/Zc:wchar_t-** C++ 標準を必要とするため`wchar_t`組み込み型を指定します。 `typedef` バージョンを使用すると、移植性の問題が発生することがあります。 Visual C の以前のバージョンからアップグレードし、コンパイラ エラーが発生したかどうかは[C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) 、コードが暗黙的に変換しようとしているため、`wchar_t`に`unsigned short`、代わりに、エラーを修正するコードを変更することをお勧めします。設定の**/Zc:wchar_t-**です。  
  
 Microsoft では、`wchar_t` が 2 バイトの符号なしの値として実装されます。 詳細については`wchar_t`を参照してください[データ型の範囲](../../cpp/data-type-ranges.md)と[基本的な型](../../cpp/fundamental-types-cpp.md)です。  
  
 現在も使用して以前のコードと相互運用する必要のある新しいコードを記述する場合、`typedef`バージョンの`wchar_t`、両方のオーバー ロードを提供することができます、`unsigned short`と`__wchar_t`のバリエーション`wchar_t`と、コードをリンクできるように、コードでコンパイルされた**/Zc:wchar_t**またはなしでコンパイルされたコード。 それ以外の場合、ライブラリの 2 つの異なるビルドを提供する必要がある: 1 つは、ない**/Zc:wchar_t**有効になっています。 この場合も、以前のコードのビルドには、新しいコードをコンパイルするときに使用するコンパイラを使用することをお勧めします。 さまざまなコンパイラでコンパイルされたバイナリを混在させないでください。  
  
 ときに**/Zc:wchar_t**が指定されている**_WCHAR_T_DEFINED**と**_NATIVE_WCHAR_T_DEFINED**シンボルが定義されています。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。  
  
 コードがあるために、コンパイラ COM グローバル関数を使用する場合**/Zc:wchar_t**で既定では、ことをお勧めから comsupp.lib への明示的な参照を変更することが、[コメント プラグマ](../../preprocessor/comment-c-cpp.md)またはコマンド行: comsuppw.lib または comsuppwd.lib のいずれかにします。 (使用してコンパイルする必要がある場合**/Zc:wchar_t-**comsupp.lib を使用します)。comdef.h のヘッダー ファイルを含めると、適切なライブラリが自動的に指定されます。 コンパイラ COM サポートについては、次を参照してください。[コンパイラ COM サポート](../../cpp/compiler-com-support.md)です。  
  
 `wchar_t` 型は、C コードをコンパイルするときはサポートされません。 Visual C の準拠の問題に関する詳細については、次を参照してください。[非標準動作](../../cpp/nonstandard-behavior.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  左側のウィンドウで展開**構成プロパティ**、 **C/C++**、し、**言語**します。  
  
3.  変更、 **wchar_t をビルトイン型として扱う**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [/Zc (準拠)](../../build/reference/zc-conformance.md)