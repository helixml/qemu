# Helix Frame Export for QEMU
# Zero-copy video encoding: virtio-gpu resource -> Metal texture ->
# IOSurface -> VideoToolbox H.264 -> vsock back to guest

if host_os == 'darwin'
  helix_ss = ss.source_set()

  helix_ss.add(files('helix-frame-export.m'))

  # macOS frameworks
  helix_ss.add(dependency('appleframeworks',
                          modules: ['VideoToolbox', 'CoreVideo', 'CoreMedia',
                                   'IOSurface', 'Metal', 'Foundation']))

  # virglrenderer dependency (for virgl_renderer_resource_get_info_ext)
  helix_ss.add(virgl)

  system_ss.add_all(helix_ss)
endif
