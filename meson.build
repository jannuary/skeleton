project('skeleton',
          version: '0.1.0',
    meson_version: '>= 0.50.0',
  default_options: [ 'warning_level=2',
                   ],
)

i18n = import('i18n')

libadwaita_dep = dependency('libadwaita-1', version: '>= 1.0.0', required: false)
if not libadwaita_dep.found()
libadwaita = subproject(
  'libadwaita',
  install: false,
  default_options: [
    'examples=false',
    'package_subdir=my-project-name',
    'tests=false',
  ]
)
libadwaita_dep = libadwaita.get_variable('libadwaita_dep')
endif


subdir('data')
subdir('src')
subdir('po')

meson.add_install_script('build-aux/meson/postinstall.py')
