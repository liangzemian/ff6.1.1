FFmpeg README
=============

FFmpeg is a collection of libraries and tools to process multimedia content
such as audio, video, subtitles and related metadata.

## Changelog
* 2024-11-21:
1.修改了configure文件
```shell
打开configure文件并搜索SLIBNAME，找到如下命令行：
SLIBNAME_WITH_MAJOR='$(SLIBNAME).$(LIBMAJOR)'
LIB_INSTALL_EXTRA_CMD='$$(RANLIB)"$(LIBDIR)/$(LIBNAME)"'
SLIB_INSTALL_NAME='$(SLIBNAME_WITH_VERSION)'
SLIB_INSTALL_LINKS='$(SLIBNAME_WITH_MAJOR)$(SLIBNAME)'
替换为：
SLIBNAME_WITH_MAJOR='$(SLIBPREF)$(FULLNAME)-$(LIBMAJOR)$(SLIBSUF)'
LIB_INSTALL_EXTRA_CMD='$$(RANLIB)"$(LIBDIR)/$(LIBNAME)"'
SLIB_INSTALL_NAME='$(SLIBNAME_WITH_MAJOR)'
SLIB_INSTALL_LINKS='$(SLIBNAME)'
```
2.删除无用tag

```shell
git tag -d quic-rb0 quic-rb1 quic-rb2 Mp4.alpha N cronet-dev-rb0 cronet-dev-rb1 cronet-dev-rb2 cronet-dev-rb3 ff2.8--ijk0.3.3--dev0.3.3--rc1 ff2.8--ijk0.3.3--dev0.3.3--rc2 ff2.8--ijk0.4.1.1--dev0.3.3--rc1 ff2.8--ijk0.4.1.1--dev0.3.3--rc2 ff2.8--ijk0.4.1.1--dev0.3.3--rc3 ff2.8--ijk0.4.1.1--dev0.3.3--rc4 ff2.8--ijk0.4.4.1--dev0.3.3--rc5 ff2.8--ijk0.4.4.1--dev0.3.3--rc6 ff2.8--ijk0.4.4.1--dev0.3.3--rc7 ff2.8--ijk0.4.5.1--dev0.3.3--rc8 ff2.8--ijk0.4.5.1--dev0.3.3--rc9 ff3.0--ijk0.4.5.1--dev0.4.5--rc10 ff3.0--ijk0.5.0--dev0.4.5--rc11 ff3.1--ijk0.6.0--20160627--001 ff3.1--ijk0.6.0--20160715--001 ff3.1--ijk0.6.0--20160718--001 ff3.1--ijk0.6.0--20160811--001 ff3.1--ijk0.6.1--20160811--002 ff3.1--ijk0.6.1--20160824--001 ff3.1--ijk0.6.2--20160926--001 ff3.1--zaku0.0.0--20160701--001 ff3.2--ijk0.7.0--20161102--001 ff3.2--ijk0.7.2-20161107--001 ff3.2--ijk0.7.4--20161116--001 ff3.2--ijk0.7.5--20161205--001 ff3.2--ijk0.7.6--20170203--001 ff3.2--ijk0.7.6--20170301--001 ff3.2--ijk0.7.6--20170324--001 ff3.2--private-fix-pipe-seek ff3.3--ijk0.8.0--20170420--001 ff3.3--ijk0.8.0--20170426--001 ff3.3--ijk0.8.0--20170427--001 ff3.3--ijk0.8.0--20170512--001 ff3.3--ijk0.8.0--20170518--001 ff3.3--ijk0.8.0--20170607--001 ff3.3--ijk0.8.0--20170615--001 ff3.3--ijk0.8.0--20170623--001 ff3.3--ijk0.8.0--20170626--001 ff3.3--ijk0.8.0--20170704--001 ff3.3--ijk0.8.0--20170707--001 ff3.3--ijk0.8.0--20170710--001 ff3.3--ijk0.8.0--20170811--001 ff3.3--ijk0.8.0--20170829--001 ff3.3--ijk0.8.0--20171219--001 ff3.3--ijk0.8.0--20171222--001 ff3.4--ijk0.8.7--20171211--001 ff3.4--ijk0.8.7--20180102--001 ff3.4--ijk0.8.7--20180103--001 ff3.4--ijk0.8.7--20180301--001 ff3.4--ijk0.8.7--20180305--001 ff3.4--ijk0.8.7--20180320--001 ff3.4--ijk0.8.7--20180322--001 ff3.4--ijk0.8.7--20180404--001 ff3.4--ijk0.8.7--20180428--001 ff3.4--ijk0.8.7--20180607--001 ff3.4--ijk0.8.7--20180612--001 ffmpeg-0.6.3 ijk-multi-io-rb0 ijk-multi-io-rb1 ijk-multi-io-rb2 ijk-multi-io-rb3 ijk-multi-io-rb5 ijk-multi-io-rb6 ijk-n0.0.1 ijk-n0.0.2 ijk-n0.0.3 ijk-n0.0.4 ijk-n0.0.6 live-test-rb0 multi-io-vod-rb0 multi-io-vod-rb1 multi-io-vod-rb2 multi-io-vod-rb2.1 n0.10 n0.10.1 n0.10.10 n0.10.11 n0.10.12 n0.10.13 n0.10.14 n0.10.15 n0.10.16 n0.10.2 n0.10.3 n0.10.4 n0.10.5 n0.10.6 n0.10.7 n0.10.8 n0.10.9 n0.11 n0.11-dev n0.11.1 n0.11.2 n0.11.3 n0.11.4 n0.11.5 n0.12-dev n0.5.10 n0.5.11 n0.5.12 n0.5.13 n0.5.14 n0.5.15 n0.5.5 n0.5.6 n0.5.7 n0.5.8 n0.5.9 n0.6.4 n0.6.5 n0.6.6 n0.6.7 n0.7.1 n0.7.10 n0.7.11 n0.7.12 n0.7.13 n0.7.14 n0.7.15 n0.7.16 n0.7.17 n0.7.2 n0.7.3 n0.7.4 n0.7.5 n0.7.6 n0.7.7 n0.7.8 n0.7.9 n0.8 n0.8.1 n0.8.10 n0.8.11 n0.8.12 n0.8.13 n0.8.14 n0.8.15 n0.8.2 n0.8.3 n0.8.4 n0.8.5 n0.8.6 n0.8.7 n0.8.8 n0.8.9 n0.9 n0.9.1 n0.9.2 n0.9.3 n0.9.4 n1.0 n1.0.1 n1.0.10 n1.0.2 n1.0.3 n1.0.4 n1.0.5 n1.0.6 n1.0.7 n1.0.8 n1.0.9 n1.1 n1.1-dev n1.1.1 n1.1.10 n1.1.11 n1.1.12 n1.1.13 n1.1.14 n1.1.15 n1.1.16 n1.1.2 n1.1.3 n1.1.4 n1.1.5 n1.1.6 n1.1.7 n1.1.8 n1.1.9 n1.2 n1.2-dev n1.2.1 n1.2.10 n1.2.11 n1.2.12 n1.2.2 n1.2.3 n1.2.4 n1.2.5 n1.2.6 n1.2.7 n1.2.8 n1.2.9 n1.3-dev n2.0 n2.0.1 n2.0.2 n2.0.3 n2.0.4 n2.0.5 n2.0.6 n2.0.7 n2.1 n2.1-dev n2.1.1 n2.1.2 n2.1.3 n2.1.4 n2.1.5 n2.1.6 n2.1.7 n2.1.8 n2.2 n2.2-dev n2.2-rc1 n2.2-rc2 n2.2.1 n2.2.10 n2.2.11 n2.2.12 n2.2.13 n2.2.14 n2.2.15 n2.2.16 n2.2.2 n2.2.3 n2.2.4 n2.2.5 n2.2.6 n2.2.7 n2.2.8 n2.2.9 n2.3 n2.3-dev n2.3.1 n2.3.2 n2.3.3 n2.3.4 n2.3.5 n2.3.6 n2.4 n2.4-dev n2.4.1 n2.4.10 n2.4.11 n2.4.12 n2.4.13 n2.4.2 n2.4.3 n2.4.4 n2.4.5 n2.4.6 n2.4.7 n2.4.8 n2.4.9 n2.5 n2.5-dev n2.5.1 n2.5.10 n2.5.11 n2.5.2 n2.5.3 n2.5.4 n2.5.5 n2.5.6 n2.5.7 n2.5.8 n2.5.9 n2.6 n2.6-dev n2.6.1 n2.6.2 n2.6.3 n2.6.4 n2.6.5 n2.6.6 n2.6.7 n2.6.8 n2.6.9 n2.7 n2.7-dev n2.7.1 n2.7.2 n2.7.3 n2.7.4 n2.7.5 n2.7.6 n2.7.7 n2.8 n2.8-dev n2.8.1 n2.8.2 n2.8.3 n2.8.4 n2.8.5 n2.8.6 n2.8.7 n2.9-dev n3.0 n3.0.1 n3.0.2 n3.1 n3.1-dev n3.1.1 n3.2 n3.2-dev n3.3 private-ff3.3-2017-0517-001 private-ff3.3-2017-0629-test-fps quick-rb0 quick-rb1 quick-rb2 quick-mp4-rb0 quick-mp4-rb1 quick-mp4-rb2 quick-mp4-rb3 quick-mp4-rb4 skip-frame-dev0 v0.5 v0.5.1 v0.5.10 v0.5.2 v0.5.3 v0.5.4 v0.5.5 v0.5.6 v0.5.7 v0.5.8 v0.5.9 v0.6 v0.6.1 v0.6.2 v0.6.3 v0.6.4 v0.6.5 v0.6.6 v0.7 v0.7.1 v0.7.2 v0.7.3 v0.7.4 v0.7.5 v0.7.6 v0.7.7 v0.7b1 v0.7b2 v0.7rc1 v0.8 v0.8.1 v0.8.10 v0.8.11 v0.8.12 v0.8.13 v0.8.14 v0.8.15 v0.8.16 v0.8.2 v0.8.3 v0.8.4 v0.8.5 v0.8.6 v0.8.7 v0.8.8 v0.8.9 v0.8b1 v0.8b2 v10 v10.1 v10.2 v10.3 v10.4 v10.5 v10_alpha1 v10_alpha2 v10_beta1 v10_beta2 v11 v11.1 v11_alpha1 v11_alpha2 v11_beta1 v11_dev0 v12_dev0 v9 v9.1 v9.10 v9.11 v9.12 v9.13 v9.14 v9.15 v9.15.1 v9.16 v9.17 v9.2 v9.3 v9.4 v9.5 v9.6 v9.7 v9.8 v9.9 v9_beta1 v9_beta2 v9_beta3 wk-v2.2 wk-v2.2a

git push origin --delete tag quic-rb0 quic-rb1 quic-rb2 Mp4.alpha N cronet-dev-rb0 cronet-dev-rb1 cronet-dev-rb2 cronet-dev-rb3 ff2.8--ijk0.3.3--dev0.3.3--rc1 ff2.8--ijk0.3.3--dev0.3.3--rc2 ff2.8--ijk0.4.1.1--dev0.3.3--rc1 ff2.8--ijk0.4.1.1--dev0.3.3--rc2 ff2.8--ijk0.4.1.1--dev0.3.3--rc3 ff2.8--ijk0.4.1.1--dev0.3.3--rc4 ff2.8--ijk0.4.4.1--dev0.3.3--rc5 ff2.8--ijk0.4.4.1--dev0.3.3--rc6 ff2.8--ijk0.4.4.1--dev0.3.3--rc7 ff2.8--ijk0.4.5.1--dev0.3.3--rc8 ff2.8--ijk0.4.5.1--dev0.3.3--rc9 ff3.0--ijk0.4.5.1--dev0.4.5--rc10 ff3.0--ijk0.5.0--dev0.4.5--rc11 ff3.1--ijk0.6.0--20160627--001 ff3.1--ijk0.6.0--20160715--001 ff3.1--ijk0.6.0--20160718--001 ff3.1--ijk0.6.0--20160811--001 ff3.1--ijk0.6.1--20160811--002 ff3.1--ijk0.6.1--20160824--001 ff3.1--ijk0.6.2--20160926--001 ff3.1--zaku0.0.0--20160701--001 ff3.2--ijk0.7.0--20161102--001 ff3.2--ijk0.7.2-20161107--001 ff3.2--ijk0.7.4--20161116--001 ff3.2--ijk0.7.5--20161205--001 ff3.2--ijk0.7.6--20170203--001 ff3.2--ijk0.7.6--20170301--001 ff3.2--ijk0.7.6--20170324--001 ff3.2--private-fix-pipe-seek ff3.3--ijk0.8.0--20170420--001 ff3.3--ijk0.8.0--20170426--001 ff3.3--ijk0.8.0--20170427--001 ff3.3--ijk0.8.0--20170512--001 ff3.3--ijk0.8.0--20170518--001 ff3.3--ijk0.8.0--20170607--001 ff3.3--ijk0.8.0--20170615--001 ff3.3--ijk0.8.0--20170623--001 ff3.3--ijk0.8.0--20170626--001 ff3.3--ijk0.8.0--20170704--001 ff3.3--ijk0.8.0--20170707--001 ff3.3--ijk0.8.0--20170710--001 ff3.3--ijk0.8.0--20170811--001 ff3.3--ijk0.8.0--20170829--001 ff3.3--ijk0.8.0--20171219--001 ff3.3--ijk0.8.0--20171222--001 ff3.4--ijk0.8.7--20171211--001 ff3.4--ijk0.8.7--20180102--001 ff3.4--ijk0.8.7--20180103--001 ff3.4--ijk0.8.7--20180301--001 ff3.4--ijk0.8.7--20180305--001 ff3.4--ijk0.8.7--20180320--001 ff3.4--ijk0.8.7--20180322--001 ff3.4--ijk0.8.7--20180404--001 ff3.4--ijk0.8.7--20180428--001 ff3.4--ijk0.8.7--20180607--001 ff3.4--ijk0.8.7--20180612--001 ffmpeg-0.6.3 ijk-multi-io-rb0 ijk-multi-io-rb1 ijk-multi-io-rb2 ijk-multi-io-rb3 ijk-multi-io-rb5 ijk-multi-io-rb6 ijk-n0.0.1 ijk-n0.0.2 ijk-n0.0.3 ijk-n0.0.4 ijk-n0.0.6 live-test-rb0 multi-io-vod-rb0 multi-io-vod-rb1 multi-io-vod-rb2 multi-io-vod-rb2.1 n0.10 n0.10.1 n0.10.10 n0.10.11 n0.10.12 n0.10.13 n0.10.14 n0.10.15 n0.10.16 n0.10.2 n0.10.3 n0.10.4 n0.10.5 n0.10.6 n0.10.7 n0.10.8 n0.10.9 n0.11 n0.11-dev n0.11.1 n0.11.2 n0.11.3 n0.11.4 n0.11.5 n0.12-dev n0.5.10 n0.5.11 n0.5.12 n0.5.13 n0.5.14 n0.5.15 n0.5.5 n0.5.6 n0.5.7 n0.5.8 n0.5.9 n0.6.4 n0.6.5 n0.6.6 n0.6.7 n0.7.1 n0.7.10 n0.7.11 n0.7.12 n0.7.13 n0.7.14 n0.7.15 n0.7.16 n0.7.17 n0.7.2 n0.7.3 n0.7.4 n0.7.5 n0.7.6 n0.7.7 n0.7.8 n0.7.9 n0.8 n0.8.1 n0.8.10 n0.8.11 n0.8.12 n0.8.13 n0.8.14 n0.8.15 n0.8.2 n0.8.3 n0.8.4 n0.8.5 n0.8.6 n0.8.7 n0.8.8 n0.8.9 n0.9 n0.9.1 n0.9.2 n0.9.3 n0.9.4 n1.0 n1.0.1 n1.0.10 n1.0.2 n1.0.3 n1.0.4 n1.0.5 n1.0.6 n1.0.7 n1.0.8 n1.0.9 n1.1 n1.1-dev n1.1.1 n1.1.10 n1.1.11 n1.1.12 n1.1.13 n1.1.14 n1.1.15 n1.1.16 n1.1.2 n1.1.3 n1.1.4 n1.1.5 n1.1.6 n1.1.7 n1.1.8 n1.1.9 n1.2 n1.2-dev n1.2.1 n1.2.10 n1.2.11 n1.2.12 n1.2.2 n1.2.3 n1.2.4 n1.2.5 n1.2.6 n1.2.7 n1.2.8 n1.2.9 n1.3-dev n2.0 n2.0.1 n2.0.2 n2.0.3 n2.0.4 n2.0.5 n2.0.6 n2.0.7 n2.1 n2.1-dev n2.1.1 n2.1.2 n2.1.3 n2.1.4 n2.1.5 n2.1.6 n2.1.7 n2.1.8 n2.2 n2.2-dev n2.2-rc1 n2.2-rc2 n2.2.1 n2.2.10 n2.2.11 n2.2.12 n2.2.13 n2.2.14 n2.2.15 n2.2.16 n2.2.2 n2.2.3 n2.2.4 n2.2.5 n2.2.6 n2.2.7 n2.2.8 n2.2.9 n2.3 n2.3-dev n2.3.1 n2.3.2 n2.3.3 n2.3.4 n2.3.5 n2.3.6 n2.4 n2.4-dev n2.4.1 n2.4.10 n2.4.11 n2.4.12 n2.4.13 n2.4.2 n2.4.3 n2.4.4 n2.4.5 n2.4.6 n2.4.7 n2.4.8 n2.4.9 n2.5 n2.5-dev n2.5.1 n2.5.10 n2.5.11 n2.5.2 n2.5.3 n2.5.4 n2.5.5 n2.5.6 n2.5.7 n2.5.8 n2.5.9 n2.6 n2.6-dev n2.6.1 n2.6.2 n2.6.3 n2.6.4 n2.6.5 n2.6.6 n2.6.7 n2.6.8 n2.6.9 n2.7 n2.7-dev n2.7.1 n2.7.2 n2.7.3 n2.7.4 n2.7.5 n2.7.6 n2.7.7 n2.8 n2.8-dev n2.8.1 n2.8.2 n2.8.3 n2.8.4 n2.8.5 n2.8.6 n2.8.7 n2.9-dev n3.0 n3.0.1 n3.0.2 n3.1 n3.1-dev n3.1.1 n3.2 n3.2-dev n3.3 private-ff3.3-2017-0517-001 private-ff3.3-2017-0629-test-fps quick-rb0 quick-rb1 quick-rb2 quick-mp4-rb0 quick-mp4-rb1 quick-mp4-rb2 quick-mp4-rb3 quick-mp4-rb4 skip-frame-dev0 v0.5 v0.5.1 v0.5.10 v0.5.2 v0.5.3 v0.5.4 v0.5.5 v0.5.6 v0.5.7 v0.5.8 v0.5.9 v0.6 v0.6.1 v0.6.2 v0.6.3 v0.6.4 v0.6.5 v0.6.6 v0.7 v0.7.1 v0.7.2 v0.7.3 v0.7.4 v0.7.5 v0.7.6 v0.7.7 v0.7b1 v0.7b2 v0.7rc1 v0.8 v0.8.1 v0.8.10 v0.8.11 v0.8.12 v0.8.13 v0.8.14 v0.8.15 v0.8.16 v0.8.2 v0.8.3 v0.8.4 v0.8.5 v0.8.6 v0.8.7 v0.8.8 v0.8.9 v0.8b1 v0.8b2 v10 v10.1 v10.2 v10.3 v10.4 v10.5 v10_alpha1 v10_alpha2 v10_beta1 v10_beta2 v11 v11.1 v11_alpha1 v11_alpha2 v11_beta1 v11_dev0 v12_dev0 v9 v9.1 v9.10 v9.11 v9.12 v9.13 v9.14 v9.15 v9.15.1 v9.16 v9.17 v9.2 v9.3 v9.4 v9.5 v9.6 v9.7 v9.8 v9.9 v9_beta1 v9_beta2 v9_beta3 wk-v2.2 wk-v2.2a

```

## Libraries

* `libavcodec` provides implementation of a wider range of codecs.
* `libavformat` implements streaming protocols, container formats and basic I/O access.
* `libavutil` includes hashers, decompressors and miscellaneous utility functions.
* `libavfilter` provides means to alter decoded audio and video through a directed graph of connected filters.
* `libavdevice` provides an abstraction to access capture and playback devices.
* `libswresample` implements audio mixing and resampling routines.
* `libswscale` implements color conversion and scaling routines.

## Tools

* [ffmpeg](https://ffmpeg.org/ffmpeg.html) is a command line toolbox to
  manipulate, convert and stream multimedia content.
* [ffplay](https://ffmpeg.org/ffplay.html) is a minimalistic multimedia player.
* [ffprobe](https://ffmpeg.org/ffprobe.html) is a simple analysis tool to inspect
  multimedia content.
* Additional small tools such as `aviocat`, `ismindex` and `qt-faststart`.

## Documentation

The offline documentation is available in the **doc/** directory.

The online documentation is available in the main [website](https://ffmpeg.org)
and in the [wiki](https://trac.ffmpeg.org).

### Examples

Coding examples are available in the **doc/examples** directory.

## License

FFmpeg codebase is mainly LGPL-licensed with optional components licensed under
GPL. Please refer to the LICENSE file for detailed information.

## Contributing

Patches should be submitted to the ffmpeg-devel mailing list using
`git format-patch` or `git send-email`. Github pull requests should be
avoided because they are not part of our review process and will be ignored.
