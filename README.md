# action-upload-release-assets

``` yaml
name: Test
on:
  push:
    tags:
      - v*

jobs:
  Linux:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Test
      shell: bash
      run: |
        echo "echo Linux > release/Linux.test"
        mkdir release
        echo Linux > release/Linux.test
    - name: Upload Release Assets
      uses: wzshiming/action-upload-release-assets@v1
      env:
        GH_TOKEN: "${{ secrets.GITHUB_TOKEN }}"
        RELEASE: release

  MacOS:
    runs-on: macos-latest
    steps:
    - uses: actions/checkout@v2
    - name: Test
      shell: bash
      run: |
        echo "echo MacOS > release/MacOS.test"
        mkdir release
        echo MacOS > release/MacOS.test
    - name: Upload Release Assets
      uses: wzshiming/action-upload-release-assets@v1
      env:
        GH_TOKEN: "${{ secrets.GITHUB_TOKEN }}"
        RELEASE: release

  Windows:
    runs-on: windows-latest
    steps:
    - uses: actions/checkout@v2
    - name: Test
      shell: bash
      run: |
        echo "echo Windows > release/Windows.test"
        mkdir release
        echo Windows > release/Windows.test
    - name: Upload Release Assets
      uses: wzshiming/action-upload-release-assets@v1
      env:
        GH_TOKEN: "${{ secrets.GITHUB_TOKEN }}"
        RELEASE: release
```
