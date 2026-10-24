import React, { useState, useRef, useEffect } from 'react';
import { CinematicVideoConfig } from '../types/wedding';
import { Play, Pause, Volume2, VolumeX, FastForward, Film, Sparkles, AlertCircle, Heart } from 'lucide-react';

interface CinematicVideoIntroProps {
  config: CinematicVideoConfig;
  guestName?: string;
  onOpenInvitation: () => void;
  onSkipVideo: () => void;
  onEnableAudio?: () => void;
}

export const CinematicVideoIntro: React.FC<CinematicVideoIntroProps> = ({
  config,
  guestName = 'Tamu Undangan',
  onOpenInvitation,
  onSkipVideo,
  onEnableAudio,
}) => {
  const videoRef = useRef<HTMLVideoElement | null>(null);
  const [isPlaying, setIsPlaying] = useState(true);
  const [isMuted, setIsMuted] = useState(true);
  const [hasError, setHasError] = useState(false);
  const [isLoading, setIsLoading] = useState(true);
  const [quality, setQuality] = useState<'auto' | '1080p' | 'saver'>('auto');

  // Determine video source safely
  const getVideoSource = () => {
    if (quality === 'saver') return config.videoUrl || config.videoUrl1080p;
    return config.videoUrl1080p || config.videoUrl;
  };

  const currentSource = getVideoSource();

  useEffect(() => {
    setHasError(false);
  }, [currentSource]);

  useEffect(() => {
    const video = videoRef.current;
    if (!video || !currentSource) return;

    setIsLoading(true);

    const onCanPlay = () => {
      setIsLoading(false);
      video
        .play()
        .then(() => setIsPlaying(true))
        .catch(() => {
          setIsPlaying(false);
        });
    };

    const onError = () => {
      setHasError(true);
      setIsLoading(false);
      setIsPlaying(false);
    };

    video.addEventListener('canplay', onCanPlay);
    video.addEventListener('error', onError);

    // Initial attempt
    const playPromise = video.play();
    if (playPromise !== undefined) {
      playPromise
        .then(() => {
          setIsPlaying(true);
          setIsLoading(false);
        })
        .catch(() => {
          setIsPlaying(false);
        });
    }

    return () => {
      video.removeEventListener('canplay', onCanPlay);
      video.removeEventListener('error', onError);
    };
  }, [currentSource, hasError]);

  const togglePlay = () => {
    const video = videoRef.current;
    if (!video) return;

    if (video.paused) {
      video.play().then(() => setIsPlaying(true)).catch(() => setIsPlaying(false));
    } else {
      video.pause();
      setIsPlaying(false);
    }
  };

  const toggleMute = () => {
    const video = videoRef.current;
    if (!video) return;

    video.muted = !video.muted;
    setIsMuted(video.muted);
    if (!video.muted && onEnableAudio) {
      onEnableAudio();
    }
  };

  const handleOpenClick = () => {
    if (onEnableAudio) {
      onEnableAudio();
    }
    onOpenInvitation();
  };

  return (
    <div className="fixed inset-0 z-50 bg-[#04120e] flex flex-col items-center justify-between overflow-hidden select-none">
      {/* 1. Cinematic Background Video or Fallback */}
      <div className="absolute inset-0 w-full h-full overflow-hidden">
        {!hasError && currentSource ? (
          <video
            ref={videoRef}
            src={currentSource}
            poster={config.posterUrl}
            playsInline
            autoPlay
            loop={config.loop}
            muted={isMuted}
            preload="metadata"
            onLoadedData={() => setIsLoading(false)}
            onError={() => {
              setHasError(true);
              setIsLoading(false);
            }}
            className={`w-full h-full ${
              config.aspectRatio === 'cover' ? 'object-cover' : 'object-contain'
            } transition-all duration-1000 transform scale-105 filter brightness-75 contrast-105`}
          />
        ) : (
          /* Cinematic Fallback with Ambient Lighting & Poster */
          <div
            className="w-full h-full bg-cover bg-center filter brightness-65 transform scale-105 animate-pulse-glow"
            style={{ backgroundImage: `url(${config.posterUrl})` }}
          />
        )}

        {/* Cinematic Darkness & Vignette Gradients */}
        <div className="absolute inset-0 bg-gradient-to-t from-[#04120e] via-[#04120e]/45 to-[#04120e]/80" />
        <div className="absolute inset-0 bg-radial from-transparent via-[#04120e]/40 to-[#04120e]" />
      </div>

      {/* 2. Top Header Toolbar: Controls, Quality & Skip */}
      <header className="relative z-10 w-full max-w-6xl mx-auto px-4 py-5 flex items-center justify-between text-xs text-emerald-100/80">
        {/* Brand / Title indicator */}
        <div className="flex items-center gap-2">
          <Film className="w-4 h-4 text-[#d4af37]" />
          <span className="font-serif tracking-widest text-xs uppercase text-[#d4af37]">
            Cinematic Wedding Preview
          </span>
          {quality !== 'auto' && (
            <span className="px-1.5 py-0.5 rounded bg-[#d4af37]/20 border border-[#d4af37]/40 text-[10px] text-[#f7ea9b]">
              {quality.toUpperCase()}
            </span>
          )}
        </div>

        {/* Controls: Audio, Quality switch & Skip */}
        <div className="flex items-center gap-2 sm:gap-3">
          {/* Quality Switcher */}
          <div className="hidden sm:flex items-center bg-[#071f18]/80 backdrop-blur-md rounded-full p-1 border border-[#d4af37]/20 text-[11px]">
            <button
              onClick={() => setQuality('auto')}
              className={`px-2.5 py-0.5 rounded-full transition-colors cursor-pointer ${
                quality === 'auto' ? 'bg-[#d4af37] text-black font-semibold' : 'text-emerald-200/70 hover:text-white'
              }`}
            >
              Auto
            </button>
            <button
              onClick={() => setQuality('1080p')}
              className={`px-2.5 py-0.5 rounded-full transition-colors cursor-pointer ${
                quality === '1080p' ? 'bg-[#d4af37] text-black font-semibold' : 'text-emerald-200/70 hover:text-white'
              }`}
            >
              FHD
            </button>
          </div>

          {/* Mute/Unmute */}
          {!hasError && (
            <button
              onClick={toggleMute}
              className="p-2 rounded-full bg-[#071f18]/80 backdrop-blur-md border border-[#d4af37]/30 text-[#d4af37] hover:bg-[#d4af37]/20 transition-all cursor-pointer"
              title={isMuted ? 'Nyalakan Audio' : 'Bisukan Audio'}
            >
              {isMuted ? <VolumeX className="w-4 h-4" /> : <Volume2 className="w-4 h-4" />}
            </button>
          )}

          {/* Play/Pause */}
          {!hasError && (
            <button
              onClick={togglePlay}
              className="p-2 rounded-full bg-[#071f18]/80 backdrop-blur-md border border-[#d4af37]/30 text-[#d4af37] hover:bg-[#d4af37]/20 transition-all cursor-pointer"
              title={isPlaying ? 'Jeda Video' : 'Putar Video'}
            >
              {isPlaying ? <Pause className="w-4 h-4" /> : <Play className="w-4 h-4" />}
            </button>
          )}

          {/* Skip Button */}
          {config.allowSkip && (
            <button
              onClick={onSkipVideo}
              className="flex items-center gap-1.5 px-3 py-1.5 rounded-full bg-[#071f18]/80 backdrop-blur-md border border-[#d4af37]/40 text-[#f4efe6] hover:border-[#d4af37] hover:text-[#d4af37] transition-all cursor-pointer text-xs"
            >
              <span>Lewati Video</span>
              <FastForward className="w-3.5 h-3.5 text-[#d4af37]" />
            </button>
          )}
        </div>
      </header>

      {/* 3. Center Cinematic Typography & Personalized Guest Card */}
      <main className="relative z-10 w-full max-w-xl mx-auto px-4 flex flex-col items-center text-center my-auto">
        {/* Subtle decorative emblem */}
        <div className="w-12 h-12 rounded-full border border-[#d4af37]/40 flex items-center justify-center mb-4 bg-[#071f18]/60 backdrop-blur-md shadow-gold-glow animate-float">
          <Heart className="w-5 h-5 text-[#d4af37] fill-[#d4af37]/40" />
        </div>

        {/* "The Wedding Of" */}
        <p className="font-script text-3xl sm:text-4xl text-[#e6ca65] mb-2 tracking-wide drop-shadow-lg">
          {config.overlayTitle || 'The Wedding Of'}
        </p>

        {/* Couple Names */}
        <h1 className="font-serif text-2xl sm:text-3xl md:text-4xl font-extrabold text-gold-gradient tracking-wide leading-tight mb-4 drop-shadow-xl max-w-lg">
          Nur Ahmad Syaifuddin
          <span className="block font-script text-3xl sm:text-4xl text-[#e6ca65] my-1 font-normal">
            &
          </span>
          Sri Wahyuni, S.Pd.
        </h1>

        {/* Date Announcement */}
        <div className="inline-flex items-center gap-3 px-5 py-1.5 rounded-full border border-[#d4af37]/40 bg-[#071f18]/70 backdrop-blur-md shadow-gold-glow mb-6">
          <span className="w-1.5 h-1.5 rounded-full bg-[#d4af37] animate-ping" />
          <span className="font-serif text-xs sm:text-sm text-[#f7ea9b] tracking-wider uppercase font-semibold">
            Kamis, 10 Desember 2026
          </span>
          <span className="w-1.5 h-1.5 rounded-full bg-[#d4af37]" />
        </div>

        {/* Personalized Guest Badge */}
        <div className="w-full max-w-sm rounded-2xl glass-card p-4 sm:p-5 text-center mb-8 shadow-gold-glow border-gold-glow">
          <p className="text-[11px] text-[#a8c7b8] uppercase tracking-widest font-medium">
            Kepada Yth. Bapak/Ibu/Saudara/i:
          </p>
          <p className="text-lg sm:text-xl font-serif font-bold text-[#faf6ed] mt-1.5 mb-0.5 line-clamp-2">
            {guestName}
          </p>
          <p className="text-[11px] text-emerald-300/80">di Tempat</p>
        </div>

        {/* Main "Buka Undangan" Trigger Button */}
        <button
          onClick={handleOpenClick}
          className="group relative inline-flex items-center justify-center gap-3 px-10 py-4 rounded-full bg-gradient-to-r from-[#d4af37] via-[#f7ea9b] to-[#aa8216] text-[#071f18] font-serif font-bold text-base sm:text-lg tracking-wider shadow-gold-glow hover:shadow-gold-intense transform hover:scale-105 active:scale-95 transition-all duration-300 cursor-pointer"
        >
          <Sparkles className="w-5 h-5 text-[#071f18] animate-spin" style={{ animationDuration: '6s' }} />
          <span>{config.overlayButtonText || 'Buka Undangan'}</span>
          <Sparkles className="w-5 h-5 text-[#071f18] animate-pulse" />
        </button>

        {/* Hint message */}
        <p className="text-[11px] text-emerald-200/60 mt-3 flex items-center justify-center gap-1.5">
          <span>Sentuh tombol untuk membuka surat undangan 3D</span>
        </p>

        {/* Error notification if video fallback was engaged */}
        {hasError && (
          <div className="mt-4 inline-flex items-center gap-1.5 text-[11px] text-[#e6ca65]/80 bg-black/40 px-3 py-1 rounded-full">
            <AlertCircle className="w-3.5 h-3.5" />
            <span>Menampilkan mode visual sinematik foto</span>
          </div>
        )}
      </main>

      {/* 4. Bottom Footer Info Bar */}
      <footer className="relative z-10 w-full max-w-6xl mx-auto px-4 py-4 flex flex-col sm:flex-row items-center justify-between text-[11px] text-emerald-200/60 border-t border-emerald-900/40">
        <p>Kediaman Bpk. Nanak Suryana & Ibu Tatik Haryati — Dsn. Sentano Jaya KM.30 kanan</p>
        <p className="mt-1 sm:mt-0 font-serif text-[#d4af37]/80">#NurSriWedding2026</p>
      </footer>
    </div>
  );
};
