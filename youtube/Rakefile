# frozen_string_literal: true

require 'pathname'
require 'rake/clean'

rule '.mp4' do |t|
  video_id = Pathname.new(t.name).basename('.mp4').to_s

  system('youtube-dl', '--id', '-f', 'worst[ext=mp4]', '--write-sub', '--sub-lang', 'ko', '--', video_id)
end
CLEAN.include Rake::FileList.new('**/*.mp4', '**/*.vtt')

rule '.condensed.mp3' => '.mp4' do |t|
  video_id = Pathname.new(t.name).basename('.condensed.mp3').to_s

  system('subs2cia', 'condense', '-i', "#{video_id}.mp4", "#{video_id}.ko.*", '-R', '^\\[.+\\]$')
end
CLOBBER.include Rake::FileList.new('**/*.mp3')
