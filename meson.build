project(
    'mavlink_autogen',
    version: '0.1.0',
)

mavgen = find_program('pymavlink/tools/mavgen.py')

mavlink_dep = custom_target(
    'gen_mavlink_headers',
    input: [
        join_paths('xml','ardupilotmega.xml'),
    ],
    depend_files: [
        join_paths('xml','common.xml'),
        join_paths('xml','icarous.xml'),
        join_paths('xml','uAvionix.xml'),
    ],
    output: ['mavlink'],
    command: [
        mavgen,
        '--lang',
        get_option('language'),
        '--wire-protocol',
        '2.0',
        '-o',
        './@OUTPUT@',
        '@INPUT@',
    ],
    build_by_default: true
)
