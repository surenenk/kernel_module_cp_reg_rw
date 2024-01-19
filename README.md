# kernel_module_cp_reg_rw
Linux kernel module to R/W CP registers for ARM processors

Following commits are available under ChromeOS and Android kernels:

commit 2c9001b514daecea0433ed0e23fc60b1513ac379
Author: Suren Eda Naarayana Kulothungan <seda...@codeaurora.org>
Date: Fri Sep 17 17:02:25 2010 -0400

arm: common: For single cores do not use smp_call_function_single

Use smp_call_function_single only for SMP systems. For
single cores, call the function directly. Use CONFIG_SMP
to determine if its a SMP system.

Change-Id: I310d8e449ba1fd00318cb4454b3bc840f67230aa
Signed-off-by: Suren Eda Naarayana Kulothungan <seda...@codeaurora.org>

commit 42b0f68886094aa319aa9ca8da72c5ac394dd1e9
Author: Suren Eda Naarayana Kulothungan <seda...@codeaurora.org>
Date: Fri Sep 17 16:45:11 2010 -0400

arm: common: Use noinline to prevent inlining of function

Declare function as noinline so that function which changes
during run time does not get inlined and instead gets called.
Without this, the function contents get inlined while
optimization is turned on.

Change-Id: I8533b0c5a83ed48346a2846e7cd531b8907f82d8
Signed-off-by: Suren Eda Naarayana Kulothungan <seda...@codeaurora.org>

commit 825ed303a0aa035b3f43bb311208f4fdda29b1f8
Author: Suren Eda Naarayana Kulothungan <seda...@quicinc.com>
Date: Fri Feb 26 09:21:15 2010 -0500

msm: CP register access tool for Read/Write to CP registers

The tool can be used to read/write to CP registers by
passing the CP parameters through /sys interface.

Signed-off-by: Suren Eda Naarayana Kulothungan <seda...@quicinc.com>


commit 16b70998926d05cb04598986b6114628068f0b80
Author: Suren Eda Naarayana Kulothungan <seda...@quicinc.com>
Date: Fri Feb 26 09:21:15 2010 -0500

msm: CP register access tool for Read/Write to CP registers

The tool can be used to read/write to CP registers by
passing the CP parameters through /sys interface.

Signed-off-by: Suren Eda Naarayana Kulothungan <seda...@quicinc.com>

https://android.googlesource.com/kernel/msm/+/android-msm-mako-3.4-jb-mr1
