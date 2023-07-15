# Coding Rule

コーディングルールは、[Code style and language versions](https://docs.ros.org/en/humble/The-ROS2-Project/Contributing/Code-Style-Language-Versions.html?highlight=coding%20rule) を基準にしています。
コードを読みやすくすることを目的としており、ルール適用を推奨するものであり、強制するものではありません。

* Python
    * [PEP 8](https://www.python.org/dev/peps/pep-0008/)
* C++
    * [clang-format](https://clang.llvm.org/docs/index.html) によるコードフォーマット適用をしています。Ubuntuの場合、`sudo apt install clang-format`でインストールできます。
    * 「clang-format version 10.0.0.4」以降から適用可能な[clang-format](.clang-format)を使用しています。

* 関数名／変数名について
    * 英語にて意味が通じるものを使用してください。
* ROS Nodeには、日本語の名称を使用する事があります。
